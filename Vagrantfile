# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
# https://app.vagrantup.com/generic/boxes/rhel8
    config.vm.box = "generic/rhel8"

    [:virtualbox, :parallels, :libvirt, :hyperv].each do |provider|
        config.vm.provider provider do |vplh, override|
            vplh.cpus = 3
            vplh.memory = 3072
        end
    end

    config.vm.synced_folder "./", "/root/rhel"
    config.vm.network "forwarded_port", guest: 80, host: 2080

    config.vm.define "r" do |node|
    node.vm.hostname = "r"
    node.vm.provision :shell, inline: <<-SHELL
      date
    SHELL
    end
end
