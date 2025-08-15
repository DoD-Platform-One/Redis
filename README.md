<!-- Warning: Do not manually edit this file. See notes on gluon + helm-docs at the end of this file for more information. -->
# redis

![Version: 22.0.3-bb.0](https://img.shields.io/badge/Version-22.0.3--bb.0-informational?style=flat-square) ![AppVersion: 8.2.0](https://img.shields.io/badge/AppVersion-8.2.0-informational?style=flat-square) ![Maintenance Track: bb_maintained](https://img.shields.io/badge/Maintenance_Track-bb_maintained-yellow?style=flat-square)

Redis(R) is an open source, advanced key-value store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets and sorted sets.

## Upstream References

- <https://bitnami.com>
- <https://github.com/bitnami/charts/tree/main/bitnami/redis>

## Upstream Release Notes

This package has no upstream release note links on file. Please add some to [chart/Chart.yaml](chart/Chart.yaml) under `annotations.bigbang.dev/upstreamReleaseNotesMarkdown`.
Example:
```yaml
annotations:
  bigbang.dev/upstreamReleaseNotesMarkdown: |
    - [Find our upstream chart's CHANGELOG here](https://link-goes-here/CHANGELOG.md)
    - [and our upstream application release notes here](https://another-link-here/RELEASE_NOTES.md)
```

## Learn More

- [Application Overview](docs/overview.md)
- [Other Documentation](docs/)

## Pre-Requisites

- Kubernetes Cluster deployed
- Kubernetes config installed in `~/.kube/config`
- Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

- Clone down the repository
- cd into directory

```bash
helm install redis chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| hostname | string | `"dev.bigbang.mil"` |  |
| istio.enabled | bool | `false` |  |
| istio.hardened.enabled | bool | `false` |  |
| istio.hardened.outboundTrafficPolicyMode | string | `"REGISTRY_ONLY"` |  |
| istio.hardened.customServiceEntries | list | `[]` |  |
| istio.hardened.customAuthorizationPolicies | list | `[]` |  |
| istio.redis.enabled | bool | `false` |  |
| istio.redis.labels | object | `{}` |  |
| istio.redis.annotations | object | `{}` |  |
| istio.redis.gateway.port | int | `15443` |  |
| istio.redis.hosts[0] | string | `"*"` |  |
| monitoring.enabled | bool | `false` |  |
| cleanUpgrade.enabled | bool | `false` |  |
| cleanUpgrade.image | string | `"registry1.dso.mil/ironbank/big-bang/base:2.1.0"` |  |
| cleanUpgrade.resources.requests.memory | string | `"256Mi"` |  |
| cleanUpgrade.resources.requests.cpu | string | `"100m"` |  |
| cleanUpgrade.resources.limits.memory | string | `"256Mi"` |  |
| cleanUpgrade.resources.limits.cpu | string | `"100m"` |  |
| upstream.nameOverride | string | `"redis-bb"` |  |
| upstream.global.imagePullSecrets[0] | string | `"private-registry"` |  |
| upstream.global.security.allowInsecureImages | bool | `true` |  |
| upstream.image.registry | string | `"registry1.dso.mil"` |  |
| upstream.image.repository | string | `"ironbank/bitnami/redis"` |  |
| upstream.image.tag | string | `"8.2.0"` |  |
| upstream.master.resources.requests.memory | string | `"256Mi"` |  |
| upstream.master.resources.requests.cpu | string | `"100m"` |  |
| upstream.master.resources.limits.memory | string | `"256Mi"` |  |
| upstream.master.resources.limits.cpu | string | `"100m"` |  |
| upstream.replica.resources.limits.cpu | string | `"100m"` |  |
| upstream.replica.resources.limits.memory | string | `"256Mi"` |  |
| upstream.replica.resources.requests.cpu | string | `"100m"` |  |
| upstream.replica.resources.requests.memory | string | `"256Mi"` |  |
| upstream.replica.autoscaling.enabled | bool | `true` |  |
| upstream.sentinel.image.tag | string | `"8.0.2-debian-12-r2"` |  |
| upstream.sentinel.resources.requests.memory | string | `"256Mi"` |  |
| upstream.sentinel.resources.requests.cpu | string | `"100m"` |  |
| upstream.sentinel.resources.limits.memory | string | `"256Mi"` |  |
| upstream.sentinel.resources.limits.cpu | string | `"100m"` |  |
| upstream.networkPolicy.enabled | bool | `false` |  |
| upstream.networkPolicy.controlPlaneCidr | string | `"0.0.0.0/0"` |  |
| upstream.metrics.image.registry | string | `"registry1.dso.mil"` |  |
| upstream.metrics.image.repository | string | `"ironbank/bitnami/analytics/redis-exporter"` |  |
| upstream.metrics.image.tag | string | `"v1.75.0"` |  |
| upstream.metrics.resources.requests.memory | string | `"256Mi"` |  |
| upstream.metrics.resources.requests.cpu | string | `"100m"` |  |
| upstream.metrics.resources.limits.memory | string | `"256Mi"` |  |
| upstream.metrics.resources.limits.cpu | string | `"100m"` |  |
| upstream.metrics.serviceMonitor.scheme | string | `""` |  |
| upstream.volumePermissions.image.tag | string | `"12-debian-12-r46"` |  |
| upstream.volumePermissions.resources.requests.memory | string | `"256Mi"` |  |
| upstream.volumePermissions.resources.requests.cpu | string | `"100m"` |  |
| upstream.volumePermissions.resources.limits.memory | string | `"256Mi"` |  |
| upstream.volumePermissions.resources.limits.cpu | string | `"100m"` |  |
| upstream.volumePermissions.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| upstream.kubectl.enabled | bool | `false` |  |
| upstream.kubectl.image.tag | string | `"1.33.1-debian-12-r5"` |  |
| upstream.kubectl.resources.limits.memory | string | `"256Mi"` |  |
| upstream.kubectl.resources.limits.cpu | string | `"100m"` |  |
| upstream.kubectl.resources.requests.memory | string | `"256Mi"` |  |
| upstream.kubectl.resources.requests.cpu | string | `"100m"` |  |
| upstream.sysctl.image.tag | string | `"12-debian-12-r46"` |  |
| upstream.sysctl.resources.requests.memory | string | `"256Mi"` |  |
| upstream.sysctl.resources.requests.cpu | string | `"100m"` |  |
| upstream.sysctl.resources.limits.memory | string | `"256Mi"` |  |
| upstream.sysctl.resources.limits.cpu | string | `"100m"` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.

---

_This file is programatically generated using `helm-docs` and some BigBang-specific templates. The `gluon` repository has [instructions for regenerating package READMEs](https://repo1.dso.mil/big-bang/product/packages/gluon/-/blob/master/docs/bb-package-readme.md)._

