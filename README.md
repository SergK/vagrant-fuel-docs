## Vagrant provision for [fuel-docs](https://github.com/stackforge/fuel-docs) project

### Description

Use Vagrant to deploy and provision ubuntu VM with [fuel-docs](https://github.com/stackforge/fuel-docs) environment

Used and tested on:
```
Distributor ID: Ubuntu
Description:    Ubuntu 12.04.5 LTS
Release:        12.04
Codename:       precise
```

### Usage

1. vagrant and virtualbox should be already installed
2. we use our personal template for vagrant ubuntu-12-04-x64, you can build your own or download from [vagrant boxes site](http://www.vagrantbox.es/)
3. `git clone https://github.com/SergK/vagrant-fuel-docs.git`
4. `cd vagrant-fuel-docs`
    - you can edit file `Vagrantfile` if you need to forward some ports or change virtual machine parameters
5. `vagrant up`
6. open [http://localhost:8080](http://localhost:8080)

That's all

You can use `vagrant ssh` to enter the shell of box and work with project

### TODO

- Need integration with gerrit, etc
- forward folder from VM to local
