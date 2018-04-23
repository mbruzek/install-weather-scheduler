This repository contains the code to install the
[weather-scheduler](https://github.com/mbruzek/weather-scheduler) application
on a Linux computer.

## Requirements

This repository uses Ansible to install the weather-scheduler application on a
remote computer. The computer running the installer must have Ansible installed
and the remote computer must be Linux with ssh running.

## Create the inventory with the target computer

Create an inventory file with the target computer(s) IP address or hostname.
Add other connection details such as `ansible_user` and
`ansible_private_key_file` as needed or add the appropriate command line
options.

## Install

To install the weather-scheduler software on all hosts in the inventory you
will use the `ansible-playbook` command with the inventory file.
```
ansible-playbook -i inventory install.yml
```
This option will prompt you for each required variable.

## Use a variable file

You can also put all the values in a file and pass the variables in using the
command line option `-e`. Since you are dealing with passwords and API keys it
is recommended to use the
[Ansible Vault](http://docs.ansible.com/ansible/latest/user_guide/vault.html)
feature to encrypt the sensitive data so the passwords and keys are not visible
in clear text.

```
ansible-playbook -i inventory -e @vault_variable_file.yml --ask-vault-password install.yml
```
