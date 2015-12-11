# Defines our Vagrant environment
#
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "4096"]
  end

  # Hydra VM  
  config.vm.define :hydra_vm do |hydra_vm|
    hydra_vm.vm.box = "ubuntu/trusty64"
    hydra_vm.vm.hostname = "hydra_vm"
    hydra_vm.vm.network :private_network, ip: "10.0.30.11"
  end
  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/hydra-playbook.yml"
    ansible.sudo = true
  end

end
