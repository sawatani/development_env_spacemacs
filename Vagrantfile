# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "jnote" do |node|
    node.vm.box = "ubuntu/bionic64"
    node.vm.hostname = "jnote"
    node.vm.network :private_network, ip: "192.168.100.10"
  end
  if Vagrant.has_plugin?("vagrant-disksize")
    config.disksize.size = "100GB"
  end
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "80"]
    vb.memory = "4096"
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.galaxy_role_file = "requirements.yml"
    ansible.galaxy_roles_path = "~/.ansible/roles"
  end
end
