# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu-14.10"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
  	vb.name = "gonnect-mingle"
  	vb.memory = 2048
  	vb.cpus = 2
    #vb.gui = true
  
    # Use VBoxManage to customize the VM. For example to change memory:
    #vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision "ansible" do |ansible|
  	ansible.playbook = "mingle.yml"
  	ansible.sudo = true
  end
  
end
