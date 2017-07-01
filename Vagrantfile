# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
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
