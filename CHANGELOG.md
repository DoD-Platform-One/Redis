# Changelog

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [14.1.0-bb.0]
### UPGRADE NOTICE
- A clean upgrade job will run which requires complete deletion of the previous redis instance, which means downtime can be expected
- Multiple values were changed and shifted around - most importantly `password` is now `auth.password`
- By default your old password (whatever is in the secret) will be used and will override any values specified
### Changed
- Updated to Redis 6.2.2 and 14.1.0 upstream chart
