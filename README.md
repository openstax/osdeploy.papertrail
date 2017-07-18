Role Name
=========

Very simple `papertrail` configuration role.  Based on [current papertrail role in tutor-deployment](https://github.com/openstax/tutor-deployment/tree/fcd3e65e321117de70deb11663cfd7e682399950/roles/papertrail).

Requirements
------------

Ansible > 2, Ubuntu

Role Variables
--------------

`papertrail_url` -- should be vaulted -- and `papertrail_watch_files`. `rsyslog_hostname` as well.  See example.

Dependencies
------------

Depends on `osdeploy.rsyslog`.

Example Playbook
----------------

```
    - hosts: servers
      roles:
        - role:             openstax.papertrail
          rsyslog_hostname: "{{ hostvars[inventory_hostname] }}"
          papertrail_url:   "logs-something.a-papertrail-instance.com:12345"
          papertrail_watch_files:
            - path: "/var/www/application-name/log/production.log"
              unique_name: "application-name-rails-log"
            - path: "path-to-another-log-file"
              unique_name: "unique-name-for-another-log"
```


License
-------

BSD

Author Information
------------------

[OpenStax](https://github.com/openstax)
