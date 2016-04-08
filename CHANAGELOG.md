# Jekyll 3 (`jekyll3`) - Change log
 
All notable changes to this role will be documented in this file.
This role adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).
 
Remember: Make sure to update jekyll3_barc_role_version variable when a new version is released.
 
## [Unreleased][unreleased]
 
### Added

* Additional tests to ensure Jekyll can create and compile a new site

### Fixed

* Pinning Ansible to pre-2.0 version in CI
* Absolute path no longer needed for testing if Jekyll is available

### Changed

* Migrating from new Ansible Galaxy namespace, from 'BARC' to 'bas-ansible-roles-collection'
* Migrating from old Ansible Galaxy 'categories' to new 'tags' meta-data
* Refactoring to use Pristine base project - BARC flavour - version 0.2.0

## 0.1.0 - 07/12/2015

### Added

* Initial version - replaces the previous BARC 'Jekyll' role (with this 'Jekyll 3' role) with support for latest Jekyll
version
