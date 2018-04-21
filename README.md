This repository contains the code to install the
[weather-scheduler](https://github.com/mbruzek/weather-scheduler) application
on a Linux computer.

## Requirements

This repository uses Ansible to install the weather-scheduler application on a
remote computer. The computer running the installer must have Ansible installed
and the remote computer must be Linux with ssh running.

## Create the inventory with the target computer
Create the Ansible inventory file with the target computer IP or hostname
and other connection details such as `ansible_user` and
`ansible_private_key_file` as needed.

## Install
```
ansible-playbook install.yml
```

## Uninstall
```
ansible-playbook uninstall.yml
```
