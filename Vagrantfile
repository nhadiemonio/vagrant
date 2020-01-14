# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define :workstation do |workstation|
    workstation.vm.box = "ubuntu/bionic64"
    workstation.vm.hostname = "workstation"
    workstation.vm.provider "virtualbox" do |vbox|
      vbox.name = "workstation"
      vbox.memory = 2048
      vbox.cpus = 2
    end
    workstation.vm.network "private_network", :ip => "192.168.56.101", :name => "vboxnet0", :adapter => 2
  end

end
