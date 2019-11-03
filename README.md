# Ansible-skeleton
The purpose is to provide a folder structure for a new project.

Folder structure in this skeleton is somewhat opinionated. Ansible provides alternative structures.

See [Ansible best practises](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#directory-layout) for more information.

## What is included
- Folder structure and placeholder files.
- Working example role.
- Example inventories for multiple environments.
- Vagrantfile for running a virtual machine locally. See [Vagrant-README](inventories/vagrant/) for more information.

## Running example-playbook
To run the example-playbook against a running vagrant machine. Run this command in the root-directory of the project.
```ansible-playbook -i inventories/vagrant/hosts example-play.yml```
