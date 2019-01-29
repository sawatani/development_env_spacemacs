# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "jnote" do |node|
        node.vm.box = "bento/ubuntu-18.04"
        node.vm.hostname = "jnote"
        node.vm.network :private_network, ip: "192.168.100.10"
  end
end
