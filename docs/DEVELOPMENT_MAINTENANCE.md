# How to Upgrade Redis Package chart

Redis is a modified/customized version of an upstream chart. The below details the steps required to update to a new version of the Redis package.

1. To update the redis helm chart, navigate to the [upstream chart repo and folder](https://github.com/bitnami/charts/tree/main/bitnami/redis) and find the tag that corresponds to the version of this chart. Locate the dependencies in `chart/Chart.yaml` and update. Whenever a dependency is updated you need to run `helm dependencies update ./chart` to pull in the new chart. Make sure the old helm chart has been removed and the new one has been added within chart/charts.
1. Modify the `version` in `Chart.yaml` - you will want to append `-bb.x` to the chart version from upstream.
1. Update `CHANGELOG.md` adding an entry for the new version and noting all changes (at minimum should include `Updated Redis chart to x.x.x` and `Updated image versions to latest in IB (redis: x.x.x, redis-exporter: x.x.x`).
1. Generate the `README.md` updates by following the [guide in gluon](https://repo1.dso.mil/platform-one/big-bang/apps/library-charts/gluon/-/blob/master/docs/bb-package-readme.md).
1. Push up your changes, validate that CI passes in the renovate MR (or create an MR if necessary). If there are any failures follow the information in the pipeline to make the necessary updates and reach out to the team if needed.
1. Perform the steps below for manual testing. CI provides a good set of basic smoke tests but it is beneficial to run some additional checks.

## Testing new Redis version

Bigbang umbrella does not deploy Redis as a package.  Instead redis should be tested as part of the AuthService package. Follow the steps below for testing. You should perform these steps on both a clean install and an upgrade from BB master.

## Cluster setup

⚠️ Always make sure your local bigbang repo is current before deploying.

Create a k3d cluster using the [Quickstart Guide](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/docs/installation/environments/quick-start.md) as reference.

## Deploy Bigbang

   ⚠️ Note that testing against your local branch or tag is only possible if you edit the overrides file to point to your changes.

From the root of this repo, run one of the following deploy commands depending on which Keycloak you wish to reference:

For `login.dso.mil` Keycloak:

  ```sh
  helm upgrade -i bigbang ${BIGBANG_REPO_DIR}/chart/ -n bigbang --create-namespace \
  --set registryCredentials.username=${REGISTRY_USERNAME} --set registryCredentials.password=${REGISTRY_PASSWORD} \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/tests/test-values.yaml \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/chart/ingress-certs.yaml \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/docs/assets/configs/example/dev-sso-values.yaml \
  -f docs/dev-overrides/minimal.yaml \
  -f docs/dev-overrides/redis-testing.yaml
  ```

For local `keycloak.dev.bigbang.mil` Keycloak:

  ```sh
  helm upgrade -i bigbang ${BIGBANG_REPO_DIR}/chart/ -n bigbang --create-namespace \
  --set registryCredentials.username=${REGISTRY_USERNAME} --set registryCredentials.password=${REGISTRY_PASSWORD} \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/tests/test-values.yaml \
  -f https://repo1.dso.mil/big-bang/bigbang/-/raw/master/chart/ingress-certs.yaml \
  -f docs/dev-overrides/minimal.yaml \
  -f docs/dev-overrides/redis-testing-local-keycloak.yaml
  ```

- Authservice (with Redis Dependency), Keycloak
- Kiali and Monitoring (including Grafana), all with SSO enabled

## Validation/Testing Steps

1. Login to Grafana and check that Redis dashboards are receiving data. The "Redis Dashboard for Prometheus" will only populate if redis metrics are enabled.
1. Login to Prometheus and Alert Manager using SSO. These logins use the AuthService which will rely on Redis for session persistence if Redis is enabled.
1. Pull logs for AuthService controller, verify connection to Redis is established. Output should be seen in logs.
1. Pull logs for AuthService Redis Master pod, verify connection from master to replica pods is successful. Output should be seen in logs.

## Files that need integration testing

If you modify any of these things, you should perform an integration test with your branch against the rest of bigbang. Some of these files have automatic tests already defined, but those automatic tests may not model corner cases found in full integration scenarios.

- `./chart/templates/bigbang/authorization-policies`
- `./chart/templates/bigbang/dashboards/redis-dashboards.yaml`
- `./chart/templates/bigbang/istio/redis-upgrade.yaml`
- `./chart/values.yaml` if it involves any of:
  - monitoring changes
  - network policy changes
  - kyverno policy changes
  - istio hardening rule changes
  - service definition changes
  - TLS settings
  - server ingress settings
  - headless server settings (especially port or other comms settings)

Follow [the standard process](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/docs/developer/test-package-against-bb.md?ref_type=heads) for performing an integration test against bigbang.

### Big Bang Integration Testing

As part of your MR that modifies bigbang packages, you should modify the bigbang  [bigbang/tests/test-values.yaml](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/tests/test-values.yaml?ref_type=heads) against your branch for the CI/CD MR testing by enabling your packages.

- To do this, at a minimum, you will need to follow the instructions at [bigbang/docs/developer/test-package-against-bb.md](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/docs/developer/test-package-against-bb.md?ref_type=heads) with changes for Redis enabled (the below is a reference, actual changes could be more depending on what changes where made to Redis in the pakcage MR).

### [test-values.yaml](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/tests/test-values.yaml?ref_type=heads)

```yaml
addons:
  authservice:
    enabled: true
    git:
      tag: ""
      branch: "your-branch"
    values:
      monitoring:
      enabled: true
      redis:
        enabled: true
      redis-bb:
        upstream:
          monitoring:
            enabled: true
          metrics:
            enabled: true # To test redis-exporter image
  ### Additional compononents of Redis should be changed to reflect testing changes introduced in the package MR
```

### automountServiceAccountToken

The mutating Kyverno policy named `update-automountserviceaccounttokens` is leveraged to harden all ServiceAccounts in this package with `automountServiceAccountToken: false`. This policy is configured by namespace in the Big Bang umbrella chart repository at [chart/templates/kyverno-policies/values.yaml](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/chart/templates/kyverno-policies/values.yaml?ref_type=heads).

This policy revokes access to the K8s API for Pods utilizing said ServiceAccounts. If a Pod truly requires access to the K8s API (for app functionality), the Pod is added to the `pods:` array of the same mutating policy. This grants the Pod access to the API, and creates a Kyverno PolicyException to prevent an alert.
