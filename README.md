# perun-ansible-rsyslog

Ansible galaxy role cesnet.rsyslog that installs and configures rsyslog.

## Requirements


## Role variables
* rsyslog_configuration_files - List of rsyslog configuration files which will be copied to /etc
* rsyslog_configuration_templates - List of rsyslog configuration templates which will be copied to /etc

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
    rsyslog_configuration_templates:
      - rsyslog.conf.jinja2
      - rsyslog.d/example_service.conf.jinja2
  roles:
    - cesnet.rsyslog
```