# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "Repo" do |vmconfig| 
    vmconfig.vm.box = 'generic/centos8'
    vmconfig.vm.hostname = 'Repo'
    vmconfig.vm.network "private_network", ip: "192.168.56.10"
    vmconfig.vm.provider "virtualbox" do |vbx|
      vbx.memory = "2048"
      vbx.cpus = "2"
    end
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
    ansible.inventory_path = "hosts"
    ansible.host_key_checking = "false"
  end
end
