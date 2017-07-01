# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  # Machine
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |v|
    v.cpus = 1
    v.memory = 1024
  end
  # Network
  config.vm.network "private_network", ip: "192.168.2.10"
  config.vm.network "forwarded_port", guest: 8080, host: 8080 
  # Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.groups = {
        "webservers" => ["default"],
        "dev_enviroment" => ["default"]
    }
    ansible.playbook = "playbook.yml"
  end
end
