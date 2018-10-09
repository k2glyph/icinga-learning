# -*- mode: ruby -*-

# vi: set ft=ruby :



# All Vagrant configuration is done below. The "2" in Vagrant.configure

# configures the configuration version (we support older styles for

# backwards compatibility). Please don't change it unless you know what

# you're doing.

Vagrant.configure("2") do |config|
  config.vm.define "control" do |ctl|
   ctl.vm.box = "ubuntu/xenial64"
   ctl.vm.hostname = "ubuntu-control"
   ctl.vm.network "private_network", ip: "192.168.56.2"
   ctl.vm.provider "virtualbox" do |vb|
     vb.memory = 1024
   end
  end
 end