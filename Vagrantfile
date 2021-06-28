# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_IMAGE = "bento/ubuntu-20.04"
ES1_IP = "192.168.99.101"
ES2_IP = "192.168.99.102"
KIBANA_IP = "192.168.99.103"
LOGSTASH_IP = "192.168.99.104"

Vagrant.configure("2") do |config|   

  config.vm.synced_folder '.', '/vagrant', disabled: true      

  config.vm.define "es1" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "es1" 
    subconfig.vm.network :private_network, ip: ES1_IP
    
    # subconfig.vm.synced_folder "./elasticsearch/es1/data", "/var/lib/elasticsearch", type: "virtualbox"
    # subconfig.vm.synced_folder "./elasticsearch/es1/log", "/var/log/elasticsearch", type: "virtualbox"

    subconfig.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu-es1"
      vb.gui = false
      vb.memory = "2048"
    end

  end
  
  config.vm.define "es2" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "es2" 
    subconfig.vm.network :private_network, ip: ES2_IP

    # subconfig.vm.synced_folder "./elasticsearch/es2/data", "/var/lib/elasticsearch", type: "virtualbox"
    # subconfig.vm.synced_folder "./elasticsearch/es2/log", "/var/log/elasticsearch", type: "virtualbox"

    subconfig.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu-es2"
      vb.gui = false
      vb.memory = "2048"
    end

  end

  config.vm.define "kibana" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "kibana" 
    subconfig.vm.network :private_network, ip: KIBANA_IP

    # subconfig.vm.synced_folder "./kibana/data", "/var/lib/kibana", type: "virtualbox"
    # subconfig.vm.synced_folder "./kibana/log", "/var/log/kibana", type: "virtualbox"

    subconfig.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu-kibana"
      vb.gui = false
      vb.memory = "1024"
    end

  end

  config.vm.define "logstash" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "logstash" 
    subconfig.vm.network :private_network, ip: LOGSTASH_IP

    # subconfig.vm.synced_folder "./logstash/data", "/var/lib/logstash", type: "virtualbox"
    # subconfig.vm.synced_folder "./logstash/log", "/var/log/logstash", type: "virtualbox"

    subconfig.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu-logstash"
      vb.gui = false
      vb.memory = "1024"
    end

  end
  
end
