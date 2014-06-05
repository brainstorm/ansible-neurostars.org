# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubuntu_13.10"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/saucy/current/saucy-server-cloudimg-amd64-vagrant-disk1.box"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  config.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
      vb.customize ["modifyvm", :id, "--memory", "1024"]
      vb.customize ["modifyvm", :id, "--cpus", "1"]
  end

  # Pull Docker Container
  config.vm.provision :docker do |container|
      container.pull_images "nicholsn/miniconda"
  end

  # Install ansible inside Vagrant and provision remote machine(s) from there
  config.vm.provision "shell" do |s|
    s.inline = "apt-get update"
    s.inline += "&& apt-get install -y python-pip python-dev"
    s.inline += "&& pip install ansible"
    s.inline += "&& ansible-galaxy install nicholsn.miniconda"
	s.inline += "&& ansible-playbook -i /etc/ansible/roles/nicholsn.miniconda/hosts /etc/ansible/roles/nicholsn.miniconda/local.yml -v"
  end

  # Checkout neurostars.org deployer 
  config.vm.provision "shell" do |s|
    s.inline = "apt-get install -y git"
    s.inline += "&& ansible-galaxy install brainstorm.neurostars_org"
  end
end
