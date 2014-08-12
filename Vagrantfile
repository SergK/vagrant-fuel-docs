# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

# if we have already clone project just skip this hook
# but the best way is to use vagrant plugins
system('if [ ! -d ./fuel-docs/.git ] ; then git clone https://github.com/stackforge/fuel-docs;fi')

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu-12-04-x64"

  config.vm.provider "virtualbox" do |v|
        v.memory = 1048
        v.cpus = 1
  end

  config.vm.provision :shell, path: "./.bootstrap/fuel-docs_bootstrap.sh"

  config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.synced_folder "fuel-docs/", "/home/vagrant/fuel-docs"

end
