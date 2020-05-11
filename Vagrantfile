# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "debian/contrib-buster64"
    config.vm.hostname = "ssl-server"

    config.vm.network "forwarded_port", id: "http", guest: 80, host: 8080
    config.vm.network "forwarded_port", id: "https", guest: 443, host: 4433

    config.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook.yml"
    end
end
