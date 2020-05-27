# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
    config.vm.define "jupiter" do |workstation|
        workstation.vm.box = "debian/buster64"

        workstation.vm.provision "ansible" do |ansible|
            ansible.playbook = "provisioning/pb.workstation.yml"
        end
    end
    
    config.vm.define "saturn" do |workstation|
        workstation.vm.box = "debian/buster64"

        workstation.vm.provision "ansible" do |ansible|
            ansible.playbook = "provisioning/pb.workstation.yml"
        end
    end
    
    config.vm.define "uranus" do |workstation|
        workstation.vm.box = "debian/buster64"

        workstation.vm.provision "ansible" do |ansible|
            ansible.playbook = "provisioning/pb.workstation.yml"
        end
    end

    config.vm.define "ipa" do |ipa|
        ipa.vm.box = "centos/7"

        ipa.vm.network "public_network", ip: "192.168.178.26", bridge: "wlp3s0"

        ipa.vm.provider "virtualbox" do |v|
            v.cpus = 2
            v.memory = 2048
        end

        ipa.vm.provision "ansible" do |ansible|
            ansible.playbook = "provisioning/pb.ipa.yml"
            ansible.extra_vars = {
                ipaserver_hostname: "ipa.test.local",
                ipaserver_domain: "test.local",
                ipaserver_realm: "TEST.LOCAL"
            }
        end
    end
end