[![CI](https://app.travis-ci.com/franzudev/ansible.svg?branch=main)](https://app.travis-ci.com/franzudev/ansible)

Ansible test
=========

Trying ansible with travis-ci, molecule, ansible-lint

### Pre-Requirements

- [Vagrant](https://www.vagrantup.com/downloads)
- [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [Docker](https://docs.docker.com/get-docker/)
- [Molecule](https://molecule.readthedocs.io/en/latest/)

### Usage


```shell
# to manage partitions
export VAGRANT_EXPERIMENTAL="disks"
 
vagrant up --provision
```
Will provision two centos/8 VMs, then install and expose Docker through tls connection on each machine.
