# -*- mode: ruby -*-
# vi: set ft=ruby

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false
    
    # set default settings
    config.vm.box = ""
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
	vb.cpu = 1
    end

    config.vm.define :ctf01, primary: true do |machine|
        machine.vm.host_name = "ctf01.local"
        machine.vm.network "private_network", ip: "10.13.37.10"
	machine.vm.provider "virtualbox" do |vb|
 	    vb.cpus = 1
	end
	machine.vm.synced_folder "data/", "/home/vagrant/Documents"
	machine.vm.provision "file", source: "~/.vagrant.d/insecure_private_key", destination: "$HOME/.ssh/id_rsa"  
     end
end
