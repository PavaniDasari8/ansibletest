# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  #config.vm.box = "ubuntu/trusty64" 
  config.ssh.insert_key = false  
  config.vm.define "vm2" do |vm2|  
    vm2.vm.box = "ubuntu/trusty64"
    vm2.vm.network "private_network", ip: "192.168.33.11"
    vm2.vm.hostname = "vm2"
    vm2.vm.synced_folder ".","/vagrant"
    vm2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
    vm2.vm.provision "shell", inline: <<-shell
      sudo apt-get update
      sudo apt-get install software-properties-common
      sudo apt-add-repository --yes --update ppa:ansible/ansible
      sudo apt-get install ansible
    shell
  end
  config.vm.define "vm3" do |vm3|
    vm3.vm.box = "ubuntu/trusty64"
    vm3.vm.network "private_network", ip: "192.168.33.12"
    vm3.vm.hostname = "vm3"
    vm3.vm.synced_folder ".","/vagrant"
    vm3.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
  end
end

