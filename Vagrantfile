# -*- mode: ruby -*-
# vi: set ft=ruby :

# https://www.vagrantup.com/docs/multi-machine/

# Vagrant.configure("2") do |config|

    ## ganymed ###
    # 
    # config.vm.define "ganymed", autostart: false do |ganymed|
        # ganymed.vm.box = "debian/buster64"
        # ganymed.vm.hostname = "ganymed"
    # 
        # ganymed.vm.network "public_network", bridge: [
            # "wlp3s0"
        # ]
    # 
        # config.vm.provision "ansible" do |ansible|
            # ansible.playbook = "pb.ganymed.yml"
            # ansible.inventory_path = "hosts"
        # end
    # end

    ## huginn ###

    # config.vm.define "huginn", autostart: false do |huginn|
        # huginn.vm.box = "debian/buster64"
        # huginn.vm.hostname = "huginn"
    # 
        # huginn.vm.network "public_network", bridge: [
            # "wlp3s0"
        # ]
    # 
        # config.vm.provision "ansible" do |ansible|
            # ansible.playbook = "pb.huginn.yml"
            # ansible.inventory_path = "hosts"
        # end
    # end

    ## workstations ###

    # config.vm.define "jupiter", autostart: false do |jupiter|
        # jupiter.vm.box = "debian/buster64"
        # jupiter.vm.hostname = "jupiter"

        # jupiter.vm.network "public_network", bridge: [
            # "wlp3s0"
        # ]

        # config.vm.provision "ansible" do |ansible|
            # ansible.playbook = "pb.workstations.yml"
            # ansible.inventory_path = "hosts"
        # end
    # end

    # config.vm.define "saturn", autostart: false do |saturn|
        # saturn.vm.box = "debian/buster64"
        # saturn.vm.hostname = "saturn"

        # saturn.vm.network "public_network", bridge: [
            # "wlp3s0"
        # ]

        # config.vm.provision "ansible" do |ansible|
            # ansible.playbook = "pb.workstations.yml"
            # ansible.inventory_path = "hosts"
        # end
    # end

# end

Vagrant.configure("2") do |config|

    config.vm.box = "debian/buster64"
  
    config.vm.define "ganymed"
    config.vm.define "huginn"
    config.vm.define "jupiter"
    config.vm.define "saturn"

    config.vm.provision "ansible" do |ganymed|
        ganymed.playbook = "pb.ganymed.yml"
        ganymed.groups = { "ganymed" => [ "ganymed" ] }
    end

    config.vm.provision "ansible" do |huginn|
        huginn.playbook = "pb.huginn.yml"
        huginn.groups = { "huginn" => [ "huginn" ] }
    end

    config.vm.provision "ansible" do |workstations|
        workstations.playbook = "pb.workstations.yml"
        workstations.groups = { "workstations" => [ "jupiter", "saturn" ] }
    end

  end