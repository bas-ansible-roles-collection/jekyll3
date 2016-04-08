# Jekyll 3 (`jekyll3`)
 
Master: [![Build Status](https://semaphoreci.com/api/v1/bas-ansible-roles-collection/jekyll3/branches/master/badge.svg)](https://semaphoreci.com/bas-ansible-roles-collection/jekyll3)
Develop: [![Build Status](https://semaphoreci.com/api/v1/bas-ansible-roles-collection/jekyll3/branches/develop/badge.svg)](https://semaphoreci.com/bas-ansible-roles-collection/jekyll3)
 
Installs Jekyll 3 static site generator

**Part of the BAS Ansible Role Collection (BARC)**

**This role uses version 0.2.0 of the https://github.com/bas-ansible-roles-collection/jekyll3.git flavour of the BAS Base Project - Pristine**.

## Overview

* Installs the Jekyll static website generator via its Ruby Gem to be globally available

## Quality Assurance

This role uses manual and automated testing to ensure its features work as advertised. 
See [here](tests/README.md) for more information.

## Dependencies

* [**bas-ansible-roles-collection.ruby2**](https://galaxy.ansible.com/bas-ansible-roles-collection/ruby2/)
  * Minimum version: *0.2.0*

More information on role dependencies is available in the 
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-dependencies)

## Requirements

* None

More information on role requirements is available in the 
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-requirements)

## Limitations

* None

More information on role limitations is available in the 
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-limitations)

## Usage

### BARC Manifest

By default, BARC roles will record that they have been applied to a system, this is termed the BAS Manifest.
The specific local facts set for this role are:

* `ansible_local.barc_jekyll3.general.role_applied` - (boolean) records whether a role has been applied
* `ansible_local.barc_jekyll3.general.role_version` - (string) records the version of the role that was applied

Note: You **SHOULD** use this feature to determine whether this role has been applied to a system.
If you do not want these facts to be set by this role, you **MUST** skip the **BARC_SET_MANIFEST** tag.

More information is available in the 
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-Manifest)

### Jekyll version

By default this role will install the latest version of Jekyll, from version *3.0* up to *4.0*. In the vast majority of
cases this behaviour is fine and the exact version is not important.

In cases where it is however, the *jekyll3_gem_version* variable be set to another version deemed valid by Ruby Gems.

### Initial Jekyll site

This role does not support creating skeleton sites since it is assumed you only need to do this once within a project.

Where you are creating a new site you can use the `jekyll new [site name]` sub-command to create a new site.

### Typical playbook

```yaml
---

- name: ...
  hosts: all
  become: yes
  vars: []
  roles:
    - bas-ansible-roles-collection.jekyll3
```

### Tags

BARC roles use standardised tags to control which aspects of an environment are changed by roles.
Tasks in this role will 'tag' themselves with these tags as appropriate, typically in `tasks/main.yml`.

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Appendix-B---BARC-Standardised)

### Variables

#### *jekyll3_barc_role_name*

* **MUST NOT** be specified
* Specifies the name of this role within the BAS Ansible Roles Collection (BARC) used for setting local facts
* See the *BARC roles manifest* section for more information
* Example: `jekyll3` 
 
#### *jekyll3_barc_role_version*
 
* **MUST NOT** be specified
* Specifies the name of this role within the BAS Ansible Roles Collection (BARC) used for setting local facts
* See the *BARC roles manifest* section for more information
* Example: `2.0.0` 

#### *jekyll3_gem_version*

* **MAY** be specified
* Specifies the version of Jekyll to install
* This value is passed directly to Ruby Gems
* Values **MUST** use a valid version constraint, as determined by Ruby Gems
* Where not specified, a value of `~>3.0` will be assumed, which translates into versions above *3.0* and below *4.0*
* Default: `~>3.0`

## Developing

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the 
[BAS Ansible Roles Collection](
https://jira.ceh.ac.uk/projects/BARC) (BARC) project on Jira.

This service is currently only available to BAS or NERC staff, although external collaborators can be added on request.
See our contributing policy for more information.

More information is also available in the
[BARC General Documentation](
https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Issue-Tracking)

### Source code

All changes should be committed, via pull request, to the canonical repository:

`ssh://git@stash.ceh.ac.uk:7999/barc/ROLE-NAME.git` 

A read-only mirror of this repository is maintained on GitHub:

`git@github.com:bas-ansible-roles-collection/ROLE-NAME.git`

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Source-Code)

### Contributing policy

This project welcomes contributions, see `CONTRIBUTING.md` for our general policy.

### Release procedure

The general release procedure for BARC roles is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Release-procedures)

## Licence

Copyright 2016 NERC BAS.

Unless stated otherwise, all documentation is licensed under the Open Government License - version 3.
All code is licensed under the MIT license.

Copies of these licenses are included within this project.
