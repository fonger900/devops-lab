# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Cấu hình cho VMware Fusion
  config.vm.provider "vmware_desktop" do |v|
    v.gui = false             # Chạy ẩn không hiện cửa sổ
    v.allowlist_verified = true
  end

  # --- Node 1: Load Balancer (Ubuntu 24.04) ---
  config.vm.define "lb" do |lb|
    lb.vm.box = "bento/ubuntu-24.04"
    lb.vm.hostname = "lb"
    lb.vm.network "private_network", ip: "192.168.56.10"
    
    lb.vm.provider "vmware_desktop" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end

  # --- Node 2: Web Server 1 (Rocky Linux 9) ---
  config.vm.define "web1" do |web1|
    web1.vm.box = "bento/rockylinux-9"
    web1.vm.hostname = "web1"
    web1.vm.network "private_network", ip: "192.168.56.11"
    
    web1.vm.provider "vmware_desktop" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end

  # --- Node 3: Web Server 2 (Rocky Linux 9) ---
  config.vm.define "web2" do |web2|
    web2.vm.box = "bento/rockylinux-9"
    web2.vm.hostname = "web2"
    web2.vm.network "private_network", ip: "192.168.56.12"
    
    web2.vm.provider "vmware_desktop" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end
end
