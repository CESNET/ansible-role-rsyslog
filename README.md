# perun-ansible-rsyslog

Ansible galaxy role cesnet.rsyslog that installs and configures rsyslog.

## Requirements


## Role variables
* rsyslog_dirs
  * List of directories which will be created
  * Example value:
    ```
    rsyslog_dirs:
    - { path: "/etc/rsyslog.d", owner: "root", group: "root", mode: "0644"}
    ```
    * where:
      * path - required
      * owner - optional - default 'root'
      * group - optional - default 'root'
      * mode - optional - default '0755'
* rsyslog_files
  * List of rsyslog configuration files which will be copied to /etc
  * Example value:
    ```
    rsyslog_files:
    - { src: "rsyslog.d/app1.conf", dest: "rsyslog.d/app1.conf", owner: "root", group: "root", mode: "0644"}
    ```
    * where:
      * src - required
      * dest - recommended; if not set, 'src' will be used; Relative to '/etc/'
      * owner - optional - default 'root'
      * group - optional - default 'root'
      * mode - optional - default '0644'
* rsyslog_templates
  * List of rsyslog configuration templates which will be copied to /etc
  * Example value:
    ```
    rsyslog_templates:
    - { src: "rsyslog.d/app1.conf", dest: "rsyslog.d/app1.conf", owner: "root", group: "root", mode: "0644"}
    ```
    * where:
      * src - required; without '.j2'
      * dest - recommended; if not set, 'src' will be used; Relative to '/etc/'
      * owner - optional - default 'root'
      * group - optional - default 'root'
      * mode - optional - default '0644'

## Available tags
* install
* configuration

## Example playbook
```
- hosts: all
  remote_user: root
  vars:
    rsyslog_dirs:
      - { path: "/etc/rsyslog.d" }
    rsyslog_files:
      - { src: "rsyslog.d/example_service.conf", dest: "rsyslog.d/service1.conf" }
    rsyslog_templates:
      - { src: "rsyslog.d/example_service.conf", dest: "rsyslog.d/service2.conf"}
  roles:
    - cesnet.rsyslog
```
