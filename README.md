# Jekyll 3 (`jekyll3`)

Master:

Develop:

Installs Jekyll 3 static site generator

**Part of the BAS Ansible Role Collection (BARC)**

## Overview

* Installs the Jekyll static website generator via its Ruby Gem

## Quality Assurance

This role uses manual and automated testing to ensure the features offered by this role work as advertised. 
See `tests/README.md` for more information.

## Dependencies

* [**BARC.ruby2**](https://galaxy.ansible.com/detail#/role/6814) - minimum version: *0.1.0*

### Pinning dependencies

All dependencies of this role will use the latest role version. In many cases this will be unsuitable and so versions
should be 'pinned' to a specific version to ensure breaking changes for example are introduced. This issue becomes
increasingly important the longer a project is not updated.

A method developed for BAS projects uses a `roles.yml` file to specify all roles, including dependencies of roles, 
and their version. This does require you to resolve dependencies for roles manually, however dependencies are listed in
each role's `meta/main.yml` and `README.md` file.

Note: BAS projects **SHOULD** always pin role versions, except in exceptional circumstances.

### Avoiding dependencies

All dependencies of this role are tagged as *BARC_ROLE_DEPENDENCY*. Skipping this tag when executing a playbook that
includes this role will prevent role dependencies from being installed.

E.g.

```shell
$ ansible-playbook playbook.yml --skip-tags "BARC_ROLE_DEPENDENCY"
```

Note: This 'dependency' tag is shared across all BARC roles, and skipping it will therefore exclude all dependencies,
from all BARC roles. There is currently no supported method to exclude only this roles dependencies.

Note: Using this role without its dependencies is **NOT** supported, and may lead to incomplete results or errors.

## Requirements

* None

## Limitations

* None

## Usage

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

- name: install jekyll
  hosts: all
  become: yes
  vars: []
  roles:
    - BARC.jekyll3
```

### Tags

BARC roles use standardised tags to control which aspects of an environment are changed by roles. Where relevant, tags
will be applied at a role, or task(s) level, as indicated below.

This role uses the following tags for various tasks:

* [**BARC_INSTALL**](https://antarctica.hackpad.com/BARC-Standardised-Tags-AviQxxiBa3y#:h=BARC_INSTALL)
* [**BARC_INSTALL_PACKAGES**](https://antarctica.hackpad.com/BARC-Standardised-Tags-AviQxxiBa3y#:h=BARC_INSTALL_PACKAGE)

### Variables

#### *jekyll3_gem_version*

* **MAY** be specified
* Specifies the version of Jekyll to install
* This value is passed directly to Ruby Gems
* Values MUST use a valid version constraint, as determined by Ruby Gems
* Where not specified, a value of `~>3.0` will be assumed, which translates into versions above *3.0* and below *4.0*
* Default: `~>3.0`

## Developing

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the 
[BAS Ansible Role Collection](https://jira.ceh.ac.uk/projects/BARC) (BARC) project on Jira.

This service is currently only available to BAS or NERC staff, although external collaborators can be added on request.
See our contributing policy for more information.

### Source code

All changes should be committed, via pull request, to the canonical repository, which for this project is:

`ssh://git@stash.ceh.ac.uk:7999/barc/jekyll3.git`

A mirror of this repository is maintained on GitHub. Changes are automatically pushed from the canonical repository to
this mirror, in a one-way process.

`git@github.com:antarctica/ansible-jekyll3.git`

Note: The canonical repository is only accessible within the NERC firewall. External collaborators, please make pull 
requests against the mirrored GitHub repository and these will be merged as appropriate.

### Contributing policy

This project welcomes contributions, see `CONTRIBUTING.md` for our general policy.

The [Git flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/) 
workflow is used to manage the development of this project:

* Discrete changes should be made within feature branches, created from and merged back into develop 
(where small changes may be made directly)
* When ready to release a set of features/changes, create a release branch from develop, update documentation as 
required and merge into master with a tagged, semantic version (e.g. v1.2.3)
* After each release, the master branch should be merged with develop to restart the process
* High impact bugs can be addressed in hotfix branches, created from and merged into master (then develop) directly

## Licence

Copyright 2015 NERC BAS.

Unless stated otherwise, all documentation is licensed under the Open Government License - version 3. All code is
licensed under the MIT license.

Copies of these licenses are included within this role.



