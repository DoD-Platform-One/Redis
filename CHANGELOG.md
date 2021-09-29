# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

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
