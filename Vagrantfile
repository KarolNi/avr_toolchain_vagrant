# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  config.vm.box = "bento/fedora-latest"

  config.ssh.password = "vagrant"  # FIXME

  config.vm.provision :shell, inline: <<-SHELL
    sudo dnf -y install avr-binutils avr-gcc avr-gcc-c++ avr-libc avrdude make automake git # avr-gdb
    sudo dnf -y install git
  SHELL

  config.vm.synced_folder "..", "/files"

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--usb", "on"]
    vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'USBtiny', '--vendorid', '0x1781', '--productid', '0x0c9f']
    vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'USBASP', '--vendorid', '0x16c0', '--productid', '0x05dc']
  end
end
