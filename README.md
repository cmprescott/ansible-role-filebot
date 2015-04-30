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

```yaml
# --- Defaults | All OS ---
filebot_version: 4.5.6
filebot_mirror: "http://downloads.sourceforge.net/project/filebot/filebot/FileBot_{{ filebot_version }}"


# --- Defaults | OS Specific  ---
filebot_deb:
  i386: "filebot_{{ filebot_version }}_i386.deb"
  x86_64: "filebot_{{ filebot_version }}_amd64.deb"


# --- Variables | Deb  ---
filebot_deb_url: "{{ filebot_mirror }}/{{ filebot_deb[ansible_architecture] }}"
filebot_deb_tmp: "/tmp/{{ filebot_deb[ansible_architecture] }}"
filebot_deb_bin: /usr/bin/filebot
```

Dependencies
------------

**TODO:** Handle Java 8 JRE dependency 

Example Playbook
----------------

```yaml
- hosts: servers.file
  roles:
     - role: ansible-role-filebot
```

License
-------

BSD

Author Information
------------------

Prescott Chris
