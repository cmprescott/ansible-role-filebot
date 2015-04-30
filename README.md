Ansible Role: FileBot
=========
[![Build Status](https://travis-ci.org/cmprescott/ansible-role-filebot.svg?branch=master)](https://travis-ci.org/cmprescott/ansible-role-filebot)

Installs FileBot 4.5 and handles dependencies

Requirements
------------

```shell
# Ansible version 1.6+
ansible --version

# JRE 1.8+
java -version

# Linux needs apt, OS X needs homebrew cask
case $OSTYPE in
  "linux"*)
      apt --version;;
  "darwin"*)
      brew cask --version;;
esac
```

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
