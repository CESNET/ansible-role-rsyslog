# perun-ansible-rsyslog

Ansible galaxy role cesnet.rsyslog that installs and configures rsyslog.

## Requirements


## Role variables
* rsyslog_configuration_files - List of rsyslog configuration files which will be copied to /etc

## Available tags
* install
* configuration

## Example playbook
```
- hosts: all
  remote_user: root
  vars:
    rsyslog_configuration_files:
      - rsyslog.conf
      - rsyslog.d/example_service.conf
  roles:
    - cesnet.rsyslog
```