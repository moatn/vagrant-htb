# -*- mode: ruby -*-
# vi: set ft=ruby

Vagrant.configure("2") do |config|
    # ssh settings
    config.ssh.insert_key = false
    config.ssh.extra_args = ["-D", "1080"]

    # base box settings
    config.vm.box = "moatn/kali-minimal"
    config.vm.box_version = "0.2"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
	vb.cpus = 2
	vb.gui = false
	vb.customize ['modifyvm', :id, '--audio', 'none']
	vb.customize ["modifyvm", :id, "--usb", "off"]
	vb.customize ["modifyvm", :id, "--usbehci", "off"]
    end

    # kali machine setttings
    config.vm.define :kali01, primary: true do |machine|
        machine.vm.host_name = "kali01.local"
        machine.vm.network "private_network", ip: "10.13.37.10"
        machine.vm.provider "virtualbox" do |vb|
            vb.cpus = 2
        end

        # extra kali provisioning/synced folders
	    machine.vm.synced_folder "data/", "/home/vagrant/Documents"

        machine.vm.provision "ansible_local", preserve_order: true do |ansible|
            ansible.playbook = "provision/kali.yml"
            ansible.install_mode = :pip
            ansible.pip_install_cmd = "sudo apt install python3 python3-pip -y"
            ansible.compatibility_mode = '2.0'
        end
    end

    # room for extra machine config here 

end
