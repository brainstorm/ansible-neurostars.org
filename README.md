Biostar-Central Ansible Roles
=============================

Initial deployment role for NeuroStars.org website. Should deploy a biostars1-based website. There are two provisioning options:

Install in a bare-metal machine or local VM in your datacenter
==============================================================


    ansible-playbook roles/neurostars.org/site.yml -i 10.0.100.50,


Or using a local Vagrant installation instead
=============================================

    git clone https://github.com/brainstorm/ansible-neurostars.org.git && cd ansible-neurostars.org && vagrant up

Or, setting it up in any of the popular cloud providers
=======================================================

Tweak the settings in roles/neurostars.org/group_vars/all

export AWS_ACCESS_KEY_ID=<aws key id>
export AWS_ACCESS_KEY=<aws secret key id>
