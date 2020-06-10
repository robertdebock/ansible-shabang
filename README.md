# Ansible SHABANG

## A way to test integration of Ansible roles

To test Ansible Roles, this environment can be used. The goal of this repository is to:
- Quickly test combinations of roles
- Demonstrate how [these Ansible Roles](https://robertdebock.nl) can be used.

## Overview

All machines get:
- auto_update
- bootstrap
- common
- core_dependencies
- firewall
- selinux
- update
- users
- zabbix_agent
- zabbix_repository

```text
+--- jenkins ---+   +--- artifactory ---+            +--- management ------+
| - java        |   | - java            |            | - ansible           |
| - jenkins     |   | - artifactory     |            | - buildtools        |
+---------------+   +-------------------+            | - python_pip        |
                                                     | - httpd             |
+--- subversion ------+    +--- mediawiki -------+   | - mysql             |
| - subversion        |    | - epel              |   | - php               |
| - zabbix_repository |    | - python_pip        |   | - remi              |
| - zabbix_agent      |    | - remi              |   | - roundcubemail     |
+---------------------+    | - php               |   | - rundeck           |
                           | - httpd             |   | - dovecot           |
 +--- zabbix_server ---+   | - mediawiki         |   | - epel              |
 | - zabbix_repository |   | - zabbix_repository |   +---------------------+
 | - zabbix_server     |   | - zabbix_agent      |
 | - zabbix_agent      |   +---------------------+ 
 +---------------------+
```

## Setup
Download all roles first.

```
ansible-galaxy install --role-file roles/requirements.yml
```

Next start machine locally.

```
vagrant up
```

Remember to `vagrant destroy` when you're done testing.

## Build (or rebuild)

```
ansible-playbook playbook.yml
```

## Organization of plays

The `playbook.yml` refers plays in `fragments/`. These fragments can be started individually too.
