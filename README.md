Ansible Role: FileBot
=========
[![Build Status](https://travis-ci.org/cmprescott/ansible-role-filebot.svg?branch=master)](https://travis-ci.org/cmprescott/ansible-role-filebot)

Installs [FileBot][filebot]. Templates kick-off script for [AMC][amc].

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
# Package/System configuration
filebot_version: 4.5.6
filebot_mirror: "http://downloads.sourceforge.net/project/filebot/filebot/FileBot_{{ filebot_version }}"

# OS Specific
filebot_deb:
  i386: "filebot_{{ filebot_version }}_i386.deb"
  x86_64: "filebot_{{ filebot_version }}_amd64.deb"

# Script to kick-off FileBot's "Automated Media Control" groovy script
filebot_amc_path: "~/filebot.amc.sh"
filebot_amc_inputs: []
filebot_amc_cli_args:
  - 'log-file ~/amc.log'
  - 'action copy' 
  - 'conflict override -non-strict'
filebot_amc_defs: 
  - 'music=y'
  - 'artwork=y'
  - '"seriesFormat=~/Videos/TV/{n}/Season {s.pad(2)}/{n}.{s00e00}.{t} ({y})"'
  - '"movieFormat=~/Videos/Films/{n} ({y})/{n}"'
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

[filebot]: http://www.filebot.net/
[amc]: http://www.filebot.net/forums/viewtopic.php?t=215