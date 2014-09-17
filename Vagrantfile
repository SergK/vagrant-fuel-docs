# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

# if we have already clone project just skip this hook
# but the best way is to use vagrant plugins
# we need to get path to Vagrantfile 
# in order not to git clone each time if we are in some other vagrant "subfolder"
system({"VPATH" => File.dirname(__FILE__)}, "if [ ! -d ${VPATH}/fuel-docs/.git ] ; then git clone https://github.com/stackforge/fuel-docs ${VPATH}/fuel-docs;fi")


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu-12-04-x64"

  config.vm.provider "virtualbox" do |v|
	v.customize ["modifyvm", :id, "--name", "fuel-docs"]
	v.customize ["modifyvm", :id, "--memory", "2048"]
	v.customize ["modifyvm", :id, "--cpus", "1"]
	v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.provision :shell, path: "./.bootstrap/fuel-docs_bootstrap.sh"

  config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.synced_folder "fuel-docs/", "/home/vagrant/fuel-docs"
  # we don't need default "sync" folder
  config.vm.synced_folder ".", "/vagrant", disabled: true

end
