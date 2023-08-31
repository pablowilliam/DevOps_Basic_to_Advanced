# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "master" do |vm1|
    vm1.vm.hostname = "master"
    vm1.vm.box = "ubuntu/focal64"
    vm1.vm.network "private_network", ip: "192.168.33.11"
    
    vm1.vm.provider "virtualbox" do |vb|
      vb.name = "master"
      vb.gui = false
      vb.memory = "1024"
    end
    vm1.vm.provision "shell", inline: <<-'SHELL'
      sudo apt-get update && apt-get install -y vim
      sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
      sudo systemctl restart ssh sshd
    SHELL
  end

  config.vm.define "centos" do |vm2|
    vm2.vm.hostname = "centos"
    vm2.vm.box = "centos/7"
    vm2.vm.network "private_network", ip: "192.168.33.12"
    
    vm2.vm.provider "virtualbox" do |vb|
      vb.name = "centos"
      vb.gui = false
      vb.memory = "512"
    end
    vm2.vm.provision "shell", inline: <<-'SHELL'
      sudo yum install -y vim
      sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
      sudo systemctl restart sshd
    SHELL
  end

  config.vm.define "oracle" do |vm3|
    vm3.vm.hostname = "oracle"
    vm3.vm.box = "generic/oracle8"
    vm3.vm.network "private_network", ip: "192.168.33.13"
    
    vm3.vm.provider "virtualbox" do |vb|
      vb.name = "oracle"
      vb.gui = false
      vb.memory = "1024"
    end
    vm3.vm.provision "shell", inline: <<-'SHELL'
      sudo yum install -y vim
      sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
      sudo systemctl restart sshd
    SHELL
  end

  config.vm.define "ubuntu" do |vm4|
    vm4.vm.hostname = "ubuntu"
    vm4.vm.box = "ubuntu/focal64"
    vm4.vm.network "private_network", ip: "192.168.33.14"
    
    vm4.vm.provider "virtualbox" do |vb|
      vb.name = "ubuntu"
      vb.gui = false
      vb.memory = "512"
    end
    vm4.vm.provision "shell", inline: <<-'SHELL'
      sudo apt-get update && apt-get install -y vim
      sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
      sudo systemctl restart ssh sshd
    SHELL
  end
  end
  