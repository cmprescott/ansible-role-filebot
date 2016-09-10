Ansible Role: FileBot
=========
[![Build Status](https://travis-ci.org/cmprescott/ansible-role-filebot.svg?branch=master)](https://travis-ci.org/cmprescott/ansible-role-filebot)

Installs [FileBot][filebot]. Templates kick-off script for [AMC][amc].

Requirements
------------

```shell
# Ansible version 2.0.0.2+
ansible --version

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
# --- Defaults/Params ---
# Package configuration
filebot_version: 4.7.2
filebot_mirror: "http://downloads.sourceforge.net/project/filebot/filebot/FileBot_{{ filebot_version }}"

# Script to kick-off FileBot's "Automated Media Control" groovy script
filebot_amc_path: "~/filebot.amc.sh"
filebot_amc_inputs: []
filebot_amc_cli_args: []
#  - 'log-file ~/amc.log'
#  - 'action copy' 
#  - 'conflict override -non-strict'
filebot_amc_defs: []
#  - 'music=y'
#  - 'artwork=y'
#  - '"seriesFormat=~/Videos/TV/{n}/Season {s.pad(2)}/{n}.{s00e00}.{t} ({y})"'
#  - '"movieFormat=~/Videos/Films/{n} ({y})/{n}"'

# --- OS Specific ---
# Deb 
filebot_deb:
  i386: "filebot_{{ filebot_version }}_i386.deb"
  x86_64: "filebot_{{ filebot_version }}_amd64.deb"
filebot_deb_url: "{{ filebot_mirror }}/{{ filebot_deb[ansible_architecture] }}"
filebot_deb_tmp: "/tmp/{{ filebot_deb[ansible_architecture] }}"
filebot_deb_bin: /usr/bin/filebot
```

Dependencies
------------

None.

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