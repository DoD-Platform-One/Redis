# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [24.0.0-bb.0] (2025-12-09)

### Updated

- Updated redis 23.2.12 -> 24.0.0
- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter v1.79.0 -> v1.80.1
- Updated registry1.dso.mil/ironbank/bitnami/redis 8.2.2 -> 8.2.3
- Updated registry1.dso.mil/ironbank/opensource/redis/redis8-slim 8.2.2 -> 8.4.0

## [23.2.12-bb.0] (2025-10-24)
### Updated

- Updated redis 23.1.1 -> 23.2.12
- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter v1.78.0 -> v1.79.0

## [23.1.1-bb.1] (2025-10-22)
### Removed

- Removed the common dependency
- Updated references to common.names.name to the nameOverrides in values.yaml

## [23.1.1-bb.0] (2025-10-16)
### Updated

- Updated redis (source) 22.0.7 -> 23.1.1

## [22.0.7-bb.3] (2025-10-10)
### Updated

- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter (source) v1.77.0 -> v1.78.0

## [22.0.7-bb.2] (2025-10-09)
### Updated

- Updated registry1.dso.mil/ironbank/bitnami/redis (source) 8.2.1 -> 8.2.2

## [22.0.7-bb.1] (2025-09-18)
### Updated

- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter (source) v1.76.0 -> v1.77.0
- Updated registry1.dso.mil/ironbank/bitnami/redis (source) 8.2.0 -> 8.2.1

## [22.0.7-bb.0] (2025-08-29)
### Updated

- Updated redis (source) 22.0.4 -> 22.0.7
- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter (source) v1.75.0 -> v1.76.0

## [22.0.4-bb.1] (2025-08-28)
### Updated

- Added fullnameOverride set to redis-bb
- Added networkPolicies to values.yaml for cleanUpgrade

## [22.0.4-bb.0] (2025-08-19)
### Updated

- Updated redis (source) 22.0.3 -> 22.0.4

## [22.0.3-bb.0] (2025-08-14)
### Updated

- Updated redis chart 21.2.13 -> 22.0.3
- registry1.dso.mil/ironbank/bitnami/redis 8.0.3 -> 8.2.0
- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter (source) v1.74.0 -> v1.75.0

## [21.2.13-bb.0] (2025-07-28)
### Updated

- Updated redis 21.2.9 -> 21.2.13

## [21.2.9-bb.1] (2025-06-24)
### Changed

- Implemented pass-through pattern

## [21.2.9-bb.0] (2025-07-08)
### Changed
- registry1.dso.mil/ironbank/bitnami/redis 8.0.2 -> 8.0.3

## [21.2.3-bb.0] (2025-06-18)
### Changed

- Updated redis chart to 21.2.3
- Updated registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter (source) v1.73.0 -> v1.74.0

## [21.1.11-bb.0] (2025-06-03)
### Changed
- registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter v1.72.1 -> v1.73.0
- registry1.dso.mil/ironbank/bitnami/redis 8.0.1 -> 8.0.2

## [21.1.3-bb.0] (2025-05-21)
### Changed
- Updated redis chart to 21.1.3
- docker.io/bitnami/kubectl 1.33.0 -> 1.33.1
- registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter v1.71.0 -> v1.72.1
- registry1.dso.mil/ironbank/bitnami/redis 8.0.0 -> 8.0.1

## [21.0.2-bb.0] (2025-05-08)

### Changed
- Updated chart to 21.0.2
- docker.io/bitnami/kubectl 1.32.4 -> 1.33.0
- registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter v1.70.0 -> v1.71.0
- registry1.dso.mil/ironbank/bitnami/redis 7.4.3 -> 8.0.0

## [20.13.2-bb.0] - 2025-05-05

### Changed
- Updated registry1.dso.mil/ironbank/bitnami/redis (source) 7.4.2 -> 7.4.3
- Updated Chart version to 20.13.2

## [20.13.0-bb.0] - 2025-04-16

### Changed
- Changed registry1.dso.mil/ironbank/bitnami/analytics/redis-exporter (source) v1.69.0 -> v1.70.0
- Updated Chart version to 20.13.0

## [20.11.4-bb.1] - 2025-03-28

### Changed
- Changed redis exporter version tag from 1.69.0 -> v1.69.0

## [20.11.4-bb.0] - 2025-03-26

### Changed
- Updated Chart version to 20.11.4
- Updated ironbank/bitnami/analytics/redis-exporter: v1.68.0 -> v.1.69.0

## [20.11.3-bb.0] - 2025-03-10

### Changed
- Updated Chart version to 20.11.3
- Updated ironbank/bitnami/analytics/redis-exporter: v1.67.0 -> v1.68.0

## [20.9.0-bb.0] - 2025-02-24

### Changed

- Updated Chart version 20.9.0
- Updated docker.io/bitnami/kubectl (source) 1.32.1-debian-12-r3 -> 1.32.2-debian-12-r3

## [20.6.2-bb.2] - 2025-02-03

### Changed

- Updated networkPolicies to networkPolicy

## [20.6.2-bb.1] - 2025-01-28

### Changed

- Updated docker.io/bitnami/kubectl (source) 1.31.2-debian-12-r3 -> 1.32.1-debian-12-r3

## [20.6.2-bb.0] - 2025-01-10

### Changed

- Updated registry1.dso.mil/ironbank/bitnami/redis 7.4.1 -> 7.4.2

## [20.6.0-bb.0] - 2024-12-18

### Changed

- Updated ironbank/bitnami/analytics/redis-exporter: v1.66.0 -> v1.67.0
- Updated chart to 20.6.0

## [20.2.1-bb.4] - 2024-11-01

### Changed

- Updated  ironbank/bitnami/analytics/redis-exporter: v1.65.0 -> v1.66.0
- Added the maintenance track annotation and badge

## [20.2.1-bb.3] - 2024-10-29

### Removed

- Reverted old Kiali label changes

## [20.2.1-bb.2] - 2024-10-22

### Changed

- Updated  ironbank/bitnami/kubectl: 1.31.1-debian-12-r3 -> 1.31.2-debian-12-r3

## [20.2.1-bb.1] - 2024-10-22

### Changed

- Updated  ironbank/bitnami/analytics/redis-exporter: v1.64.1 -> v1.65.0

## [20.2.1-bb.0] - 2024-10-15

### Changed

- Updated chart version to redis/20.2.1
- Updated ironbank/bitnami/analytics/redis-exporter: v1.63.0 -> v1.64.1

## [20.1.7-bb.0] - 2024-10-04

### Changed

- Updated chart version to redis/20.1.7
- Updated registry1.dso.mil/ironbank/bitnami/redis 7.4.0 -> 7.4.1

## [20.0.1-bb.1] - 2024-09-10

### Changed

- Updated redis-exporter image to 1.63.0

## [20.0.1-bb.0] - 2024-08-14

### Changed

- Updated chart version to redis/20.0.1

## [19.6.2-bb.1] - 2024-07-30

### Changed

- Modified redis-prometheus-dashboard to fix grafana dashboards

## [19.6.2-bb.0] - 2024-07-22

### Changed

- Updated redis-exporter image to 1.62.0
- Updated chart version to redis/19.6.2

## [19.5.5-bb.2] - 2024-07-17

### Changed

- Added default values for `master.podLabels` and `replica.podLabels` to set `app` and `version` as required by Kiali

## [19.5.5-bb.1] - 2024-07-15

### Changed

- Removed shared authorization policies

## [19.5.5-bb.0] - 2024-06-07

### Changed

- Updated chart to 19.5.5
- Updated redis-exporter from 1.60.0 to 1.61.0

## [19.5.0-bb.1] - 2024-06-07

### Changed

- Updated redis-exporter from 1.59.0 to 1.60.0 (including security fixes for the prometheus golang client from 1.19.0 to 1.19.1)
- Updated bitnami/kubectl from 1.29.2-debian-12-r3 to 1.30.0-debian-12-r3 (doc updates for vmware, deprecated Contour 1.25 Kubectl 1.26 and Dokuwiki 20230404, add notes re Bitnami package signing process - irrelevant for Iron Bank users, others see <https://blog.bitnami.com/2024/03/bitnami-packaged-containers-and-helm.html>)
- Updated DEVELOPMENT_MAINTENANCE instructions for new bitnami chart tagging practice, redis-exporter source, and bitnami container images

## [19.5.0-bb.0] - 2024-05-23

### Changed

- Updated chart to 19.5.0
- Updatd registry1.dso.mil/ironbank/bitnami/redis 7.2.4 -> 7.2.5

## [19.3.2-bb.0] - 2024-05-15

### Changed

- Updated chart to 19.3.2
- Updatd redis-exporter from v1.58.0 to v1.59.0

## [18.15.0-bb.2] - 2024-04-25

### Changed

- Added istio whitelisting configuration

## [18.15.0-bb.1] - 2024-04-18

### Changed

- Fixed bug with missing grafana dashboard data when Thanos is enabled

## [18.15.0-bb.0] - 2024-02-22

### Changed

- Updated chart to 18.15.0
- Updatd redis-exporter from v1.57.0 to v1.58.0

## [18.9.1-bb.0] - 2024-01-18

### Changed

- Updated chart to 18.9.1
- Updatd redis-exporter from v1.56.0 to v1.57.0

## [18.7.1-bb.1] - 2024-01-23

### Changed

- Commented out upstream empty seLinuxOptions: {} blocks--gatekeeper is blocking these

## [18.7.1-bb.0] - 2024-01-18

### Changed

- Updated redis from 7.2.3 to 7.2.4
- Updatd redis-exporter from v1.55.0 to v1.56.0

## [18.3.2-bb.3] - 2024-01-09

### Changed

- Enabled Istio Hardening for testing

## [18.3.2-bb.2] - 2024-01-04

### Changed

- Changed some runAsGroup values to be non-root

## [18.3.2-bb.1] - 2023-11-21

### Added

- Added istio `allow-nothing` policy
- Added istio `allow-ingress` polic(y|ies)
- Added istio `allow-intranamespace` policy
- Added istio custom policy template

## [18.3.2-bb.0] - 2023-11-13

### Changed

- Updated to latest chart upstream
- Updated redis to 7.2.3
- Updated big-bang/base to 2.1.0

## [18.2.0-bb.0] - 2023-10-30

### Added

- Added support for PodMonitor
- Added grafana dashboards

### Changed

- Updated to latest chart upstream
- Updated redis to 7.2.2

## [18.1.5-bb.0] - 2023-10-16

### Changed

- Updated to latest chart upstream
- Updated redis-exporter to v1.55.0

## [18.0.4-bb.1] - 2023-10-05

### Changed

- Modified runAsGroup securityContext for redis containers

## [18.0.4-bb.0] - 2023-09-20

### Changed

- Updated to latest chart upstream
- Updated to 7.2.1 redis version
- Updated redis-exporter to v1.54.0

## [17.15.4-bb.0]

### Changed

- Updated to latest chart upstream
- Updated to 7.2.0 redis version
- Updated redis-exporter to v1.52.0

## [17.13.2-bb.0]

### Changed

- Updated to latest chart upstream
- Updated to 7.0.12 redis version

## [17.10.2-bb.1]

### Changed

- Updated imagePullSecrets to de-duplicate

## [17.10.2-bb.0]

### Changed

- Updated to Redis 7.0.11 and 17.10.2 upstream chart

## [17.9.3-bb.0]

### Changed

- Updated redis-exporter to v1.50.0

## [17.9.1-bb.0]

### Changed

- Updated redis to v7.0.10
- Updated redis-exporter to v1.48.0

## [16.12.3-bb.4]

### Changed

- Updated redis-exporter to v1.45.0

## [16.12.3-bb.3]

### Changed

- Added support foro mTLS metrics config, and scheme

## [16.12.3-bb.2]

### Added

- Added capabilities: drop: all

## [16.12.3-bb.1]

### Changed

- Updated BB base image to 2.0.0

## [16.12.3-bb.0]

### UPGRADE NOTICE

- Updated to Redis 7.0.2 and 16.12.3 upstream chart

## [16.9.2-bb.0]

### UPGRADE NOTICE

- Updated to Redis 6.2.6 and 16.9.2 upstream chart

## [16.4.0-bb.0]

### UPGRADE NOTICE

- Updated to Redis 6.2.5 and 16.4.0 upstream chart

## [14.1.0-bb.7]

### Changed

- Fixed indentation in prometheusRule leading to errors in templating when being read by the kube-operator

## [14.1.0-bb.6]

### Changed

- Uncommented prometheusRule rule examples within chart. When enabled via BigBang, 3 prometheusRule templates will be created in cluster

## [14.1.0-bb.5]

### Changed

- Disabled clean upgrade job. Job was only needed when upgrading to Redis 6.2.2 and the 14.1.0 upstream chart. Keeping in for users upgrading from old version of BB

## [14.1.0-bb.4]

### Changed

- Removed `sidecar.istio.io/inject: 'false'` annotation from clean upgrade job and added `curl -X POST http://localhost:15020/quitquitquit` to cleanly terminate the istio sidecar container when the job completes. This was done to resolve OPA Gatekeeper violations

## [14.1.0-bb.3]

### Changed

- Updated clean upgrade job to include resource requests and limits in order to resolve OPA Gatekeeper violations

## [14.1.0-bb.2]

### Changed

- Changed cleanUpgrade image from gitlab/kubectl to bigbang/base.

## [14.1.0-bb.1]

### Added

- NetworkPolicy to ensure API access

## [14.1.0-bb.0]

### UPGRADE NOTICE

- A clean upgrade job will run which requires complete deletion of the previous redis instance, which means downtime can be expected
- Multiple values were changed and shifted around - most importantly `password` is now `auth.password`
- By default your old password (whatever is in the secret) will be used and will override any values specified

### Changed

- Updated to Redis 6.2.2 and 14.1.0 upstream chart
