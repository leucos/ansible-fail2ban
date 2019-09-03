**DEPRECATED: MOVED TO https://github.com/devops-works/ansible-fail2ban**

fail2ban Ansible role
=====================

Installs & configures fail2ban on Ubuntu 16.04+

Requirements
------------

None


Role Variables
--------------

`f2b_jails`: yaml structure containing fail2ban jails to deploy

Example
-------

```
f2b_jails:
    DEFAULT:
      destemail: "you@example.org"
      sender: "root@{{ inventory_hostname }}"
      action: "%(action_mw)s"
    ssh:
      findtime: 3600
      bantime: 86400
      maxretry: 3
      enabled: "true"
      logpath: /var/log/auth.log
      filter: sshd
      port: ssh
    mysqld-auth:
      findtime: 3600
      bantime: 864000
      maxretry: 5
      enabled: "true"
      filter: mysqld-auth
      port: 3306
      logpath: /var/log/syslog
```

License
-------

MIT

Author Information
------------------

@leucos

