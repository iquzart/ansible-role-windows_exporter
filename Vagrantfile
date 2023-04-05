# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_IMAGE = "gusztavvargadr/windows-server-2022-standard-core"
HOSTNAME = "win2022-testbox"

Vagrant.configure("2") do |config|
  
    config.vm.define "windows_server" do |ws|
      ws.vm.box = BOX_IMAGE
      # ws.vm.hostname = HOSTNAME # --> Disabled to reduce setup time
      ws.vm.guest = :windows
      ws.vm.synced_folder ".", "/vagrant", disabled: true
      ws.vm.provider "virtualbox" do |vb|
        vb.name = HOSTNAME
        vb.memory = "4096"
        vb.cpus = 2
      end
      ws.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision.yml"
        ansible.limit = "all"
        #ansible.verbose = "v"
        ansible.extra_vars = {
            ansible_winrm_scheme: "http"
        }
      end
    end
    
  end