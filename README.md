Ansible Role: FileBot
=========

Installs FileBot 4.5 and handles dependencies

Requirements
------------

**TODO:** Document supported OS

Role Variables
--------------

```yaml
filebot_pkg_install_using: 
filebot_pkg_url: 
filebot_dir_download: 
filebot_dir_install:
```

Dependencies
------------

**TODO:** Handle Java 8 JRE dependency 

Example Playbook
----------------

```yaml
- hosts: file_servers
  roles:
     - role: ansible-role-filebot
```

License
-------

BSD

Author Information
------------------

Prescott Chris
