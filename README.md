# percona_xtrabackup

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/saucelabs-ansible/percona_xtrabackup/master/LICENSE)
[![Build Status](https://travis-ci.org/saucelabs-ansible/percona_xtrabackup.svg?branch=master)](https://travis-ci.org/saucelabs-ansible/percona_xtrabackup)

[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/saucelabs-ansible-percona_xtrabackup/widgets/project_thin_badge.gif)](https://www.openhub.net/p/saucelabs-ansible-percona_xtrabackup/)

Ansible role to setup the [Percona xtrabackup for MySQL](https://www.percona.com/software/mysql-tools/percona-xtrabackup).


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Ubuntu  | Trusty  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


## Requirements

- ansible >= 1.9.4


## Role Variables

- **debug**: flag to run debug tasks (default: false).
- **percona_xtrabackup_version**: the version to be installed.

Unless stated otherwise
a default value is provided for each of the variables mentioned above
in `defaults/main.yml`.


## Dependencies

- [percona_apt](https://github.com/saucelabs-ansible/percona_apt)


## Playbooks

Example:

    - hosts: servers
      vars:
        debug: yes

      roles:
         - role: percona_xtrabackup
           tags: [ percona, xtrabackup ]


## Tags

- **debug**: role variables debug task.
- **installation**: installation tasks.
- **validation**: role variables validation task.


## Test

To run the tests you will need to install:

- [tox](https://tox.readthedocs.org/)
- [vagrant](https://www.vagrantup.com/)

To run all tests against all pre-defined OS/distributions * ansible versions:

```
$ tox
```

To run tests for `trusty64`:

```
$ cd tests
$ bash test_idempotence.sh --box trusty64.vagrant.dev
# log file will be stores under tests/log
```

To perform debugging on a specific environment:

```
$ cd tests
$ vagrant up trusty64.vagrant.dev

# to provision using the test.yml playbook (as many time as you need)
$ vagrant provision trusty64.vagrant.dev

# to access the Vagrant box
$ vagrant ssh trusty64.vagrant.dev
```


## Links

- [Percona xtrabackup for MySQL](https://www.percona.com/software/mysql-tools/percona-xtrabackup)


## Author Information

- [steenzout](https://github.com/steenzout/)
