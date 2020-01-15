# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :ubuntu do |ubuntu|
    ubuntu.vm.box = "ubuntu/bionic64"
    ubuntu.vm.hostname = "ubuntu"
    ubuntu.vm.provider "virtualbox" do |vbox|
      vbox.name = "ubuntu"
      vbox.memory = 2048
      vbox.cpus = 2
    end
    ubuntu.vm.provision "ansible" do |ansible|
      ansible.playbook = "../ansible/provision.yml"
      ansible.galaxy_roles_path = "../ansisble/roles/"
      ansible.extra_vars = {
        ansible_python_interpreter:"/usr/bin/python3"
     }
    end
    ubuntu.vm.network "private_network", :ip => "192.168.56.100", :name => "vboxnet0", :adapter => 2
  end

  config.vm.define :centos do |centos|
    centos.vm.box = "centos/7"
    centos.vm.hostname = "centos"
    centos.vm.provider "virtualbox" do |vbox|
      vbox.name = "centos"
      vbox.memory = 2048
      vbox.cpus = 2
    end
    centos.vm.provision "ansible" do |ansible|
      ansible.playbook = "../ansible/provision.yml"
      ansible.galaxy_roles_path = "../ansisble/roles/"
    end
    centos.vm.network "private_network", :ip => "192.168.56.200", :name => "vboxnet0", :adapter => 2 
  end

end
