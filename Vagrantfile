# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.define "gerrit" do |gerrit|
    gerrit.vm.box = "mrlesmithjr/trusty64"
    gerrit.vm.hostname = "gerrit"

    gerrit.vm.network :private_network, ip: "192.168.202.201"
    gerrit.vm.network "forwarded_port", guest: 8080, host: 8080

    gerrit.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
    gerrit.vm.provision :shell, path: "provision.sh", keep_color: "true"
  end
  config.vm.define "client" do |client|
    client.vm.box = "mrlesmithjr/trusty64"
    client.vm.hostname = "client"

    client.vm.network :private_network, ip: "192.168.202.202"

    client.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
  end
end