# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  def configure(c, addr, hostname)
    c.vm.box = "bento/ubuntu-16.04"
    c.vm.network :private_network, ip: addr
    c.vm.hostname = hostname
    c.vm.box_check_update = false
    c.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      vb.memory = 1024
    end
  end

  config.vm.define "fn1" do |c|
    configure c, "192.168.50.51", "fn1"
  end
  config.vm.define "fn2" do |c|
    configure c, "192.168.50.52", "fn2"
  end
  config.vm.define "fn3" do |c|
    configure c, "192.168.50.53", "fn3"
  end
end
