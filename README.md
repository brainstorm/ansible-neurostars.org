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

AWS
===

This automated deployment script assumes that you have the following in your AWS console:

1. Created a [keypair called `neurostars`](https://console.aws.amazon.com/ec2/v2/home?region=eu-west-1#KeyPairs:) in your Amazon account.
2. Locally defined both AWS_ACCESS_KEY_ID and AWS_SECRET_KEY [environment variables for your AWS user](https://console.aws.amazon.com/iam/home?region=eu-west-1#users)
3. Installed both [VirtualBox](https://www.virtualbox.org/) and [Vagrant](http://www.vagrantup.com/) on your local machine.

Then, just running `vagrant up` should suffice! :)

Google compute Engine
=====================

TBD
