=============================
Biostar-Central Ansible Roles
=============================

Initial deployment role for NeuroStars.org website. Should deploy a biostars1-based website. There are two provisioning options:

Install in a bare-metal machine or local VM in your datacenter
==============================================================

```
ansible-playbook roles/neurostars.org/site.yml -i 10.0.100.50,
```

Or using a local Vagrant installation instead
=============================================

```
git clone git@github.com:brainstorm/ansible-neurostars.org.git && cd ansible-neurostars.org && vagrant up
```
