rsyslog
========

This playbook will configure rsyslog for clients and servers. Only one server is supported and clients will be configured to send logs to the server via UDP.

Requirements
------------

RHEL/CentOS 6
Debian/Ubuntu - untested

Example Playbook
-------------
```
- hosts: all
  roles:
    - role: rsyslog
```

Role Variables
--------------

roles/common/defaults/main.yml
syslog_server: log1
If you want a different logging server it is best to configure that in one of the vars/*.yml files. This was set here as a catchall in case it was missed somewhere else.

```
roles/common/vars/defaults.yml
syslog_conf_file: rsyslog.conf
Configuration file for rsyslog
syslog_conf_path: /etc/
Path for rsyslog config file

roles/common/vars/{{ ansible_os_family }}.yml
syslog_server - commented out by default, will override defaults/main.yml if set
syslog_conf_file - specific rsyslog conf file name for distribution
syslog_conf_path - specific rsyslog path for distribution
install_packages - packages needed for rsyslog
```

Dependencies
------------

None

License
-------

BSD

Author Information
------------------

Justin Garrison

@rothgar

www.justingarrison.com
