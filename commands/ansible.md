# Installation
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```
[more](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Usage
### Pass variable to ansible playbook in the command line
```
ansible-playbook xxx.yml --extra-vars "target=path"

tasks:
- name: test
  shell: ls "{{target}}"
```
