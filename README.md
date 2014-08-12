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
7. You can work with project which is in `./fuel-docs` (we leave git repository on the host node. This helps us to use the same git configurations as on the host node are: _username, aliases, etc_ )
8. To build project use: `./build.sh` 
`Usage: ./build.sh { help | html | singlehtml | pdf | latextpdf | epub }`

That's all

You can use `vagrant ssh` to enter the shell of box

#### More information

Actually we clone project on the host system and not on the VM, this ensures us for using the same git configuration (global) options that are defined for user in the host system (_username, aliases, etc_ ).
_- So why do we need vagrant separate box? We can use **virtualenv**_
_- Actually: **YES**. But what if:
1. You host machine running Windows
2. You are running CentOS or (RHEL), of course you can install all the necessary using yum
3. You don't want to install some libSOMETING-dev in your system or any other packages that we need to build the project
**4. You want to install project with "one click"**
5. ...
_

