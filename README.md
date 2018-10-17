# Ansible : Playbook MariaDB

The aim of this project is to deploy a simple MariaDB instance on Linux Vagrant.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

*   [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
*   Update the Vagrant file based on your computer (CPU, memory), if needed
*   You must have download the ubuntu Xenial64 vagrant box :

```bash
$ vagrant box add https://app.vagrantup.com/ubuntu/boxes/xenial64
```

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Build Environment

Vagrant needs to init the project to run and build it :

```bash
$ vagrant up
```

After build, you can check which virtual machine Vagrant has created :

```bash
$ vagrant status
```

If all run like it is expected, you should see something like this :

```bash
$ vagrant status

Current machine states:

mariadb01                   running (virtualbox)
```

#### Deployment

This playbook has some dependencies to other roles that must be downloaded before executing the playbook :

```
ansible-galaxy install -r requirements.yml
```

This command should download the Epel role from Wikitops Github account to the local role path.

To deploy MariaDB on Vagrant, you just have to run the Ansible playbook mariadb.yml with this command :

```bash
$ ansible-playbook mariadb.yml
```

If everything run as expected, you should have MariaDB installed and configured on the Vagrant instance.

#### Destroy

To destroy the Vagrant resources created, just run this command :

```bash
$ vagrant destroy
```

## Author

Member of Wikitops : https://www.wikitops.io/

## Licence

This project is licensed under the Apache License, Version 2.0. For the full text of the license, see the LICENSE file.
