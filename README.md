# Ansible SHABANG

## A way to test integration of Ansible roles

To test Ansible Roles, this environment can be used. The goal of this repository is to:
- Quickly test combinations of roles
- Demonstrate how [these Ansible Roles](https://robertdebock.nl) can be used.

## Overview

```text
      FRONTEND             APPLICATION           BACKEND

+---- node1 -----+   +---- node2 -----+   +----- node3 -----+
| - httpd        |   | - zabbix_agent |   | - mysql         |
| - zabbix_agent |   |                |   | - rsyslog       |
| - ca           |   |                |   | - postfix       |
| - openvpn      |   |                |   | - httpd         |
|                |   |                |   | - zabbix-agent  |
|                |   |                |   | - zabbix-server |
|                |   |                |   | - zabbix_web    |
|                |   |                |   | - squid         |
+----------------+   +----------------+   +-----------------+
```

## Entrypoints

Once the environment is up (`vagrant up`) and running (`./playbook.yml`) you can use the entrypoints:

- Zabbix: https://Admin:zabbix@node1.example.com/zabbix
- Roundcubemail: https://node1.example.com/roundcubemail

## Settings

All roles are called in `playbook.yml` and all variable (for the roles) are set in `inventory/group_vars/*.yml`.

### Setup

Download all roles first.

```
ansible-galaxy install --role-file roles/requirements.yml
```

Next start machine locally.

```
vagrant up
```

Remember to `vagrant destroy` when you're done testing.

### Build (or rebuild)

```
ansible-playbook playbook.yml
```
