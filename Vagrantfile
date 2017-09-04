# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "web" do |ansible|
    ansible.vm.box = "ubuntu/xenial64"
    ansible.vm.network "private_network", ip: "10.0.10.15"
    ansible.vm.network :forwarded_port, guest: 22, host: 12345, auto_correct: true
    ansible.vm.network :forwarded_port, guest: 8111, host: 8111, auto_correct: true
    ansible.vm.provision "shell" do |provision|
      provision.path = "provision_ansible.sh"
    end
  end
end
