# -*- mode: ruby -*-
# vi: set ft=ruby :

imagen = "geerlingguy/ubuntu1804"

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.define "masters" do |m|
     m.vm.box = imagen
     m.vm.network "public_network"
     m.vm.hostname = "master"
     m.vm.provision :docker
     m.vm.provision :docker_compose

     m.vm.provider :virtualbox do |vb|
       vb.name = "masters"
       vb.memory = 2048
       vb.cpus = 2
       vb.check_guest_additions = false
     end
  end	

  config.vm.define "cliente" do |c|
    c.vm.box = imagen
    c.vm.network "public_network"
    c.vm.hostname = "cliente"
   
    c.vm.provider :virtualbox do |vb|
       vb.name = "cliente"
       vb.check_guest_additions = false
    end
  end
end	

