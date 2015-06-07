[![Build Status](https://travis-ci.org/mfoo/ansible-playbooks.svg)](https://travis-ci.org/mfoo/ansible-playbooks)

# Martin's Ansible Playbooks

This repository contains my [Ansible](http://www.ansible.com/home) playbooks that I use for
managing my office machine, personal desktop, a few servers, my laptops and any virtual machines /
containers that I need.

At the time of writing there is only one playbook: `bootstrap.yml`. This will run all of my  roles
across all machines in the inventory. Assigning machines to different roles will execute the
appropriate tasks on them.

The roles are tested on Ubuntu 12.04, Ubuntu 15.04, and Debian Jessie.

Current roles are as follows:

* **common** - Applies to all machines. Installs my dotfiles and essential tools. Sets my shell to
  ZSH.
* **commandline-workstation** - Installs command-line tools that I regularly use.
* **graphical-workstation** - Installs graphical tools that I regularly use. Removes useless /
  unused tools that come with default installations.
* **development-common** - I'm a software developer. This role installs software-development tools.
  These are generic tools, not language specific. I will add roles later such as
  `development-java`.
* **docker** - Installs [Docker](https://www.docker.com/).
* **cleanup** - Cleans up any packages that were installed as dependencies but their dependent is
  now removed. Happens as the last part of the bootstrap playbook.

## Getting Started

In order to use these scripts you will need three things:

1.) Ansible

`pip install ansible`

2.) This repository

`git clone https://github.com/mfoo/ansible-playbooks.git`

3.) An Ansible inventory. This by default lives at `/etc/ansible/hosts`. It might look something
like this:

```
[graphical-workstations]
192.168.0.18
192.168.0.16

[commandline-workstations]
192.168.0.18
192.168.0.16

[development-machines]
192.168.0.18
192.168.0.16
```

Once you have all of that, running Ansible is simple:

```
cd ansible-playbooks
ansible-playbook -K bootstrap.yml
```
