# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  (0..2).each do |i|
    config.vm.define "swarm-node-#{i}" do |d|
      d.vm.box = "ubuntu/bionic64"
      d.vm.hostname = "swarm-master"
      d.vm.network "private_network", ip: "10.100.192.20#{i}"
      d.vm.provider "virtualbox" do |v|
        v.memory = 2048
      end
      d.vm.provision :shell, path: "install_ansible.sh"
      d.vm.provision :shell, path: "install_docker.sh"
    end
  end
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end
end
