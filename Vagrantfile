# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  

  config.vm.provider "virtualbox" do |v|
    v.gui=false

  end
  
  ##### DEFINE VM for P #####
  config.vm.define "P" do |device|
    
    device.vm.hostname = "P" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "P"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_PE1
      device.vm.network "private_network", virtualbox__intnet: "P_PE1", auto_config: false , :mac => "a00000000021"
      # link for int2 --> to_PE2
      device.vm.network "private_network", virtualbox__intnet: "P_PE2", auto_config: false , :mac => "44383900005c"
      
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end

  ##### DEFINE VM for PE1 #####
  config.vm.define "PE1" do |device|
    
    device.vm.hostname = "PE1" 
    
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "PE1"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_P
      device.vm.network "private_network", virtualbox__intnet: "P_PE1", auto_config: false , :mac => "a00000000011"
      # link for int2 --> to_CE1A
      device.vm.network "private_network", virtualbox__intnet: "PE1_CE1A", auto_config: false , :mac => "443839000004"
      # link for int3 --> to_CE1B
      device.vm.network "private_network", virtualbox__intnet: "PE1_CE1B", auto_config: false , :mac => "443839000016"
      
    
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end


  ##### DEFINE VM for PE2 #####
  config.vm.define "PE2" do |device|
    
    device.vm.hostname = "PE2" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "PE2"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_P
      device.vm.network "private_network", virtualbox__intnet: "P_PE2", auto_config: false , :mac => "442839000021"
      # link for int2 --> to_CE2A
      device.vm.network "private_network", virtualbox__intnet: "PE2_CE2A", auto_config: false , :mac => "443839000022"
      # link for int3 --> to_CE2B
      device.vm.network "private_network", virtualbox__intnet: "PE2_CE2B", auto_config: false , :mac => "a00000000012"
      
	  
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end

  ##### DEFINE VM for CE1A #####
  config.vm.define "CE1A" do |device|
    
    device.vm.hostname = "CE1A" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "CE1A"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CORE1A
      device.vm.network "private_network", virtualbox__intnet: "CE1A_CR1A", auto_config: false , :mac => "443839000018"
      # link for int2 --> to_PE1
      device.vm.network "private_network", virtualbox__intnet: "PE1_CE1A", auto_config: false , :mac => "44383900001c"
  
	  
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end

  ##### DEFINE VM for CE1B #####
  config.vm.define "CE1B" do |device|
    
    device.vm.hostname = "CE1B" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "CE1B"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CORE1B
      device.vm.network "private_network", virtualbox__intnet: "CE1B_CR1B", auto_config: false , :mac => "44383900000e"
      # link for int2 --> to_PE1
      device.vm.network "private_network", virtualbox__intnet: "PE1_CE1B", auto_config: false , :mac => "44383900000f"
	  
      
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end


  ##### DEFINE VM for CE2A #####
  config.vm.define "CE2A" do |device|
    
    device.vm.hostname = "CE2A" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "CE2A"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CORE2A
      device.vm.network "private_network", virtualbox__intnet: "CE2A_CR2A", auto_config: false , :mac => "a00000000013"
      # link for int2 --> to_PE2
      device.vm.network "private_network", virtualbox__intnet: "PE2_CE2A", auto_config: false , :mac => "443839000029"
	  
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end


 ##### DEFINE VM for CE2B #####
  config.vm.define "CE2B" do |device|
    
    device.vm.hostname = "CE2B" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "CE2B"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 2048
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CORE2B
      device.vm.network "private_network", virtualbox__intnet: "CE2B_CR2B", auto_config: false , :mac => "443839000024"
      # link for int2 --> to_PE2
      device.vm.network "private_network", virtualbox__intnet: "PE2_CE2B", auto_config: false , :mac => "443839000030"
  
	  
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ['modifyvm', :id, '--nicpromisc3', 'allow-all', "--nictype3", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end


##### DEFINE VM for PC1A #####
  config.vm.define "PC1A" do |device|
    
    device.vm.hostname = "PC1A" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "PC1A"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 1024
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CE1A
      device.vm.network "private_network", virtualbox__intnet: "CE1A_CR1A", auto_config: false , :mac => "443839000031"
     
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end

##### DEFINE VM for PC1B #####
  config.vm.define "PC1B" do |device|
    
    device.vm.hostname = "PC1B" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "PC1B"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 1024
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CE1B
      device.vm.network "private_network", virtualbox__intnet: "CE1B_CR1B", auto_config: false , :mac => "a00000000014"
     
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end


  ##### DEFINE VM for PC2A #####
  config.vm.define "PC2A" do |device|
    
    device.vm.hostname = "PC2A" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "PC2A"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 1024
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CE2A
      device.vm.network "private_network", virtualbox__intnet: "CE2A_CR2A", auto_config: false , :mac => "443839000066"
     
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end

  ##### DEFINE VM for PC2B #####
  config.vm.define "PC2B" do |device|
    
    device.vm.hostname = "PC2B" 
    config.vm.box = "aspyatkin/ubuntu-18.04-server"
    device.vm.provider "virtualbox" do |v|
      v.name = "PC2B"
      v.customize ["modifyvm", :id, '--audiocontroller', 'AC97', '--audio', 'Null']
      v.memory = 1024
    end
    
    device.vm.synced_folder ".", "/vagrant", disabled: true
	
    # NETWORK INTERFACES
      # link for int1 --> to_CE2B
      device.vm.network "private_network", virtualbox__intnet: "CE2B_CR2B", auto_config: false , :mac => "443839000033"
     
    device.vm.provider "virtualbox" do |vbox|
      vbox.customize ['modifyvm', :id, '--nicpromisc2', 'allow-all', "--nictype2", "virtio"]
      vbox.customize ["modifyvm", :id, "--nictype1", "virtio"]
    end

end

end
