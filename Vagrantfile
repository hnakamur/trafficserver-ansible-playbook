# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/centos67"
  config.vm.network "private_network", ip: "192.168.33.131"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end
  config.cache.scope = :box if Vagrant.has_plugin? 'vagrant-cachier'
  config.vm.provision "shell", inline: <<-EOS
    sudo mkdir -p -m 700 /root/.ssh
    sudo cp /home/vagrant/.ssh/authorized_keys /root/.ssh/authorized_keys
  EOS
  # Use this settings after creating /root/.ssh/authorized_keys with provisioning
  # config.ssh.username = 'root'
end
