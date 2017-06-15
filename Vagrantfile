# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = true

  config.vm.define "register" do |web|
      web.vm.network  :private_network, ip: "192.168.34.10", bridge: "eth0"
      web.vm.hostname = "register"  
      web.vm.provider "virtualbox" do |vb|
         vb.memory = "2024"
         #vb.gui = true
      end
  end

  
 config.vm.define "client" do |web2|
     web2.vm.network :private_network, ip: "192.168.34.11", bridge: "eth0"
     web2.vm.hostname = "client"  
     web2.vm.provider "virtualbox" do |vb|
         vb.memory = "512"
         #vb.gui = true
     end
end

config.vm.provision "ansible" do |ansible|
    ansible.inventory_path = "/home/denis/vp/elk/ansible2"
    ansible.playbook = "/home/denis/vp/elk/elk.yml"
    ansible.sudo = true
end

config.vm.provision "ansible" do |ansible|
    ansible.inventory_path = "/home/denis/vp/elk/ansible2"
    ansible.playbook = "/home/denis/vp/elk/clielk.yml"
    ansible.sudo = true
end


end
