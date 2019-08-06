# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "generic/centos7"

    [:virtualbox, :parallels, :libvirt, :hyperv].each do |provider|
        config.vm.provider provider do |vplh, override|
            vplh.cpus = 2
            vplh.memory = 2048
        end
    end

    config.vm.synced_folder "./", "/root/lpic"
    config.vm.network "forwarded_port", guest: 80, host: 2080

    config.vm.define "c" do |node|
    node.vm.hostname = "c"
    node.vm.provision :shell, inline: <<-SHELL
      date
    SHELL
    end
end
