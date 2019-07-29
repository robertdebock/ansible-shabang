# Ansible SHABANG

## A way to test integration of Ansible roles

To test Ansible Roles, this environment can be used. The goal of this repository is to:
- Quickly test combinations of roles
- Demonstrate how [these Ansible Roles](https://robertdebock.nl) can be used.

## Overview

```text
+--- jenkins ---------+   +--- artifactory -----+
| - bootstrap         |   | - bootstrap         |
| - common            |   | - common            |
| - update            |   | - update            |
| - firewall          |   | - firewall          |
| - java              |   | - java              |
| - jenkins           |   | - artifactory       |
| - zabbix_repository |   | - zabbix_repository |
| - zabbix_agent      |   | - zabbix_agent      |
+---------------------+   +---------------------+

+--- subversion ------+   +--- mediawiki -------+
| - bootstrap         |   | - bootstrap         |
| - common            |   | - common            |
| - update            |   | - update            |
| - firewall          |   | - firewall          |
| - subversion        |   | - epel              |
| - zabbix_repository |   | - python_pip        |
| - zabbix_agent      |   | - remi              |
|                     |   | - php               |
|                     |   | - httpd             |
|                     |   | - mediawiki         |
|                     |   | - zabbix_repository |
|                     |   | - zabbix_agent      |
+---------------------+   +---------------------+

+--- zabbix_server ---+
| - bootstrap         |
| - zabbix_repository |
| - zabbix_server     |
| - zabbix_agent      |
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
