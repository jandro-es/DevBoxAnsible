DevBoxAnsible
=============

An Ansible - Vagrant playbook for a development box suitable for:

* LAMP
* MEAN
* Python
  
###Requirements
You need to install on your local system the following:

######Vagrant

Donwload it from <http://www.vagrantup.com/> and follow the instructions.
 
######Virtual box
Download from <https://www.virtualbox.org/> the one that suits your system
 
######Vagrant guests additions plugin

	vagrant plugin install vagrant-vbguest
	
######Ansible
On Mac OSX with Macports:
	
	sudo port install ansible
	
On Mac OSX with Homebrew:

	brew install ansible
	
###Installation
Just clone/download this repository in the base directory of the application you want to use with the box.

####Customise
You can modify the playbook - vagrant configuration to adapt it to your particular needs:

######Vagrantfile
Configure the IP and port in case it conflicts with another one:

	config.vm.network "private_network",ip: "10.0.0.7"
	config.vm.network "forwarded_port", guest: 80, host: 8080
	
######Hosts
You have to change the virtual host template to adapt it to your application:

	ServerName     local.site
	
By default is configured for a Symfony 2 development:

	RewriteRule ^(.*)$ app_dev.php [QSA,L]
	
######Your local host file
You should add an entry on you local hosts file with the IP and site name you setup:

	10.0.0.7 local.site
	
###Use
Now you can start working with the usual Vagrant commands:

	vagrant up
	vagrant ssh
	vagrant provision
	vagrant halt
	vagrant destroy
	...............
	
