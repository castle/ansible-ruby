# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.package.name = "Ansible Ruby VM"
  config.vm.box = "precise64"

  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.hostname = "ruby.local"

  config.vm.network :private_network, ip: "10.0.0.14"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1048"]
    vb.customize ["modifyvm", :id, "--cpus", 2]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "role.yml"
    ansible.inventory_path = "vagrant"
    ansible.limit = 'all'
  end
end
