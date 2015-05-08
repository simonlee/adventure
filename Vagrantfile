# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.synced_folder ".", "/home/vagrant/adventure"
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y gdb git vim
    cd /home/vagrant
    git clone https://github.com/longld/peda.git peda
    echo "source /home/vagrant/peda/peda.py" >> /home/vagrant/.gdbinit
    chown vagrant:vagrant /home/vagrant/.gdbinit
  SHELL
end
