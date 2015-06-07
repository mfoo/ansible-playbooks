[![Build Status](https://travis-ci.org/mfoo/ansible-playbooks.svg)](https://travis-ci.org/mfoo/ansible-playbooks)

This repository contains ansible playbooks to manage bootstrapping and maintenance of machines.
Apart from my office machine, personal desktop, a few servers and laptops, I regularly launch
virtual machines and containers. The playbooks here help me manage configuration and infrastructure
across all of those machines.

At the time of writing there is only one playbook: `bootstrap.yml`. This will run all of my roles
across all machines in the inventory. Assigning machines to different roles will execute the
appropriate tasks on them.
