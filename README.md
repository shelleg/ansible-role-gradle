Gradle Ansible Role  
===================

Installs Gradle 
Get from Ansible galaxy like so: 

```
ansible-galaxy install shelleg.gradle
```

Please test the role before creating a Pull Request by issuing:

```
chmod +x ./tests/geerlingguy.test/ansible-role-test.sh
cleanup=false container_id=$(date +%s) distro=centos7 ./tests/geerlingguy.test/ansible-role-test.sh
```

Build Status:
-------------
Currently only supports Ansible lint, need to add distributions (work started in `.travis.yml`)

[![Build Status](https://travis-ci.org/shelleg/ansible-role-gradle.svg?branch=master)](https://travis-ci.org/shelleg/ansible-role-gradle)

[![Code Climate](https://codeclimate.com/github/shelleg/ansible-role-gradle/badges/gpa.svg)](https://codeclimate.com/github/shelleg/ansible-role-gradle) [![Issue Count](https://codeclimate.com/github/shelleg/ansible-role-gradle/badges/issue_count.svg)](https://codeclimate.com/github/shelleg/ansible-role-gradle) [![Test Coverage](https://codeclimate.com/github/shelleg/ansible-role-gradle/badges/coverage.svg)](https://codeclimate.com/github/shelleg/ansible-role-gradle/coverage)

Requirements
------------
JAVA Oracle

Role Variables
--------------

Version related:

* `gradle_version: 4.4.1`
* `gradle_checksum: sha256:dd9b24950dc4fca7d1ca5f1ccd57ca8c5b9eb407e3e6e0f48174fde4bb19ed06`

Defaults:
 
* `gradle_binary: "gradle-{{ gradle_version }}-all.zip"`
* `gradle_download_url: "https://services.gradle.org/distributions/{{ gradle_binary }}"`

Installation directory:

* `gradle_base_dir: /usr/local/share/`
* `gradle_extract_dir:  "gradle-{{ gradle_version }}"`
* `gradle_link: /usr/local/bin/gradle`

Dependencies
------------
Requires Java in order to run.
Personally I do not believe in dependencies from meta/main.yml
considering this looks too much like black magic ...

Example Playbook
----------------

Including an example of how to use this role:
``` shell

---
- hosts: localhost
  remote_user: root
  roles:
    - java
    - gradle
```

Changelog:
----------

* initial release - initial release support ubutnu 14/16.04 && centos 6/7

License
-------

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)

Author Information
------------------

Haggai Philip Zagury <hagzag@tikalk.com> part of
[Shellg](https://github.com/shelleg/shelleg) project.
see also [Shellg Docs](http://shelleg.github.io/shellegDoc/)
