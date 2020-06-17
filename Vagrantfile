# -*- mode: ruby -*-
# vi: set ft=ruby :
#
ENV["LC_ALL"] = "en_US.UTF-8"

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  config.vm.synced_folder "./data", "/data"

  config.ssh.forward_agent = true
  config.ssh.forward_x11 = true

  config.vm.hostname = "stracs"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "stracs"
    vb.gui = false
    vb.memory = "1024"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.install_mode = "pip"
    ansible.playbook = "provisioning/playbook.yml"
  end
end
