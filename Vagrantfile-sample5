#-*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
 config.vm.box = "centos/7"

#forward 8080 port from the VM to the host OS   
 config.vm.network "forwarded_port", guest: 8080, host: 8080, host_ip: "127.0.0.1"

 config.vm.provider "virtualbox" do |vb|
 # Customize the amount of memory on the VM:
     vb.memory = "3024"
   end

config.vm.synced_folder ".", "/vagrant", disabled: true

# apply ansible playbooks 
config.vm.provision "ansible" do |ansible|
      ansible.playbook = "jenkins-blue-ocean.yml"
      ansible.verbose = "vv"
    end
end
