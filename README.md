Ansible Role: FileBot
=========

Installs FileBot 4.5 and handles dependencies

Requirements
------------

- **[Darwin](http://www.oracle.com/technetwork/java/javase/certconfig-2095354.html#os "Mac OS X ")**
  - *Mac OS X*: 10.8.3+ (Mountain Lion|Mavericks|Yosemite)
- **[Linux](http://www.oracle.com/technetwork/java/javase/certconfig-2095354.html#os "Linux (Java JRE 8)")**
  - *Debian*: 7+ (wheezy|jessie)
  - *Ubuntu*: 12.04+ (Precise|Raring|Saucy|Trusty|Utopic|Vivid)

Role Variables
--------------

**TODO:** None currently accounted for. Might want to customize install.

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
