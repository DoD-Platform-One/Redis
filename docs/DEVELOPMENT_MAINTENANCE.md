# Code Changes for Updates

Redis is a modified/customized version of an upstream chart. The below details the steps required to update to a new version of the Redis package.

1. Navigate to the [upstream chart repo and folder](https://github.com/bitnami/charts/tree/main/bitnami/redis) and find the commit hash that corresponds with the new chart version for this update (Bitnami doesn't publish tags for their charts). For example, if updating the Redis image to 7.2.2 you would check the [chart values](https://github.com/bitnami/charts/blob/main/bitnami/redis/values.yaml#L91) and identify the commit hash until you find the latest chart version that uses the 7.2.2 Redis image. Start with the newest chart version to make sure we get the latest patches.

2. From the root of the repo run `kpt pkg update chart@<commit> --strategy alpha-git-patch` replacing `<commit>` with the commit hash you got in step 1. You may be prompted to resolve some conflicts - choose what makes sense (if there are BB additions/changes keep them, if there are upstream additions/changes keep them).

3. Modify the `version` in `Chart.yaml` - you will want to append `-bb.0` to the chart version from upstream.

4. Update `CHANGELOG.md` adding an entry for the new version and noting all changes (at minimum should include `Updated Redis chart to x.x.x` and `Updated image versions to latest in IB (redis: x.x.x, redis-exporter: x.x.x)`.

5. Generate the `README.md` updates by following the [guide in gluon](https://repo1.dso.mil/platform-one/big-bang/apps/library-charts/gluon/-/blob/master/docs/bb-package-readme.md).

6. Push up your changes, validate that CI passes. If there are any failures follow the information in the pipeline to make the necessary updates and reach out to the team if needed.

7.  Perform the steps below for manual testing. CI provides a good set of basic smoke tests but it is beneficial to run some additional checks.

## Manual Testing for Updates

NOTE: For these testing steps it is good to do them on both a clean install and an upgrade. For clean install, point monitoring to your branch. For an upgrade do an install with monitoring pointing to the latest tag, then perform a helm upgrade with monitoring pointing to your branch.

Since Bigbang umbrella does not deploy Redis as a package, we can deploy Redis as part of the AuthService package:
1. Create a branch on AuthService package repo
2. Helm Package your local Redis chart and copy to the AuthService branch under authservice/chart/charts/redis.x.tgz
3. Push AuthService branch to repo1
4. Modify your BB values to use the AuthService git branch that you pushed to repo1
5. Deploy Bigbang with Monitoring and AuthService packages enabled. Set AuthService, Redis enabled to true (see below for sample values config). Deploy with SSO enabled [sample SSO values](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/docs/assets/configs/example/dev-sso-values.yaml).
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
        monitoring:
          enabled: true
        metrics:
          enabled: true # To test redis-exporter image
```
6. Login to Grafana and check that Redis dashboards are receiving data. The "Redis Dashboard for Prometheus" will only populate if redis metrics are enabled.
7. Login to Prometheus and Alert Manager using SSO. These logins use the AuthService which will rely on Redis for session persistence if Redis is enabled.
8. Pull logs for AuthService controller, verify connection to Redis is established. Output should be seen in logs.
9. Pull logs for AuthService Redis Master pod, verify connection from master to replica pods is successful. Output should be seen in logs.
10. Cleanup/Delete your AuthService branch

### automountServiceAccountToken
The mutating Kyverno policy named `update-automountserviceaccounttokens` is leveraged to harden all ServiceAccounts in this package with `automountServiceAccountToken: false`. This policy is configured by namespace in the Big Bang umbrella chart repository at [chart/templates/kyverno-policies/values.yaml](https://repo1.dso.mil/big-bang/bigbang/-/blob/master/chart/templates/kyverno-policies/values.yaml?ref_type=heads). 

This policy revokes access to the K8s API for Pods utilizing said ServiceAccounts. If a Pod truly requires access to the K8s API (for app functionality), the Pod is added to the `pods:` array of the same mutating policy. This grants the Pod access to the API, and creates a Kyverno PolicyException to prevent an alert.
