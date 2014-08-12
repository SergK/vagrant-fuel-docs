# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu-12-04-x64"

  config.vm.provider "virtualbox" do |v|
        v.memory = 1048
        v.cpus = 1
  end

  config.vm.provision :shell, path: "fuel-docs_bootstrap.sh"
  config.vm.network :forwarded_port, guest: 80, host: 8080

end