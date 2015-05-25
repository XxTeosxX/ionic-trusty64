# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.define :ionic do |ionic_config|
    ionic_config.vm.network :forwarded_port, guest: 8000, host: 8000
    ionic_config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "1048"]
      vb.customize ["modifyvm", :id, "--vram", "128"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
      vb.customize ["modifyvm", :id, "--accelerate3d", "on"]
    end
    ionic_config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end
end
