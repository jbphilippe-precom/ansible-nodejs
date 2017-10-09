[![build status](https://gitrep.services.local/ansible-middlewares/ansible-nodejs/badges/develop/build.svg)](https://gitrep.services.local/ansible-middlewares/ansible-nodejs/commits/develop)

Role Name
=========

Node.js v6 LTS installation, npm local configuration and optionally install pm2 to manage node apps.
This role coud also be used to install Node.js v4

You can also install metrology for NodeJS with this project : https://gitrep.services.local/ansible-middlewares/ansible-collectd

Requirements
------------

- Ubuntu Trusty or Xenial

Role Variables
--------------

    nodejs_major_version: "6"
    nodejs_pm2_install: False
    nodejs_user: "node"
    nodejs_group: "node"
    nodejs_logs_dir: "/var/log/node"
    nodejs_user_home: "/opt/node"
    nodejs_apps_dir: "{{ nodejs_user_home }}/apps"
    nodejs_appsconf_dir: "{{ nodejs_user_home }}/conf"


Example Playbook
----------------

Playbook example:

    - name: deploy Nodejs
      hosts: webservers
      become: yes
      vars:
        nodejs_pm2_install: True
      roles:
        - ../roles/ansible-nodejs

Playbook launch
---------------

    export ANSIBLE_HOST_KEY_CHECKING=False; ansible-playbook -i hosts playbook.yml --ask-pass --ask-become-pass --tags installation

Tags
----

- [installation] : Node.js installation
- [rollback] : does nothing yet
- [testing] : Unit testing for Node.js

License
-------

BSD

Author Information
------------------

BSO ISL
