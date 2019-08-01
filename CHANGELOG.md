# Change Log

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## Types of changes

* **Added** for new features.
* **Changed** for changes in existing functionality.
* **Deprecated** for soon-to-be removed features.
* **Removed** for now removed features.
* **Fixed** for any bug fixes.
* **Security** in case of vulnerabilities.

## 2019-05-30

### Added

* This CHANGLELOG.md

* A circular ingress policy was added to the security group for port 7785 to allow Bolt, Converter and Temporary instance to talk to each other. This provides support for Rubrik CDM 5.0.1.

* Permissions were added to support encrypted instances.

### Changed [Added functionality and resolved issues]

* The policy documents were broken up into separate documents for the CloudOut and CloudOn permissions. In some cases, we saw the policy documents on the IAM user exceeding AWS limits.

## Removed

* Removed the option to create custom named policy documents on the IAM user. Instead, fixed names are used to indicate CloudOut or CloudOn permissions. The documentation was also updated.