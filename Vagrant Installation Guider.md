# What is Vagrant?

So in simple nutshell words, Vagrant is an open-source software product that is used to manage any development environment. Using Vagrant, you can install any virtual OS using the CLI (Command Line Interface), run it, do some work, and shut it down. 

# How to Install Vagrant?
Vagrant is available for all major OS like MacOS, Windows, Linux (Redhat, Amazon Linux, Ubuntu, Debian, CentOS, Fedora, and Homebrew.)

In this Guide, we will learn how to Install Vagrant on Windows.

Download Vagrant: https://developer.hashicorp.com/vagrant/downloads.

- Download the Vagrant.exe Installer from Given Link.
- Right-Click on the installer and Click on Install.
- Specify your Install Deatination.
- Open Powershell CLI and run `vagrant -v`(it will show the version of vagrant)
- Create a folder Vagrant using CLI 'mkdir vagrant'
- We are going to run a Ubuntu Based VM for Ubuntu run the command 
```vagrant init ubuntu/trusty64```
it will create a `Vagrantfile` file in the specific folder
open this file using `notepad ./Vagrantfile`
- Put this code in the Vagrantfile
```
Vagrant.configure("2") do |config|
config.vm.box = "ubuntu/trusty64"
config.vm.hostname ="VM1"
end
```
All set now Run `vangrant up`

- now you will see your virtualbox your machine is getting ready and will start automaticly.

- you can connect your VM to your private network also, for this you have to network configration in Vegrantfile.

- add this code to set forwording port in VM
```config.vm.network "forwarded_port", guest: "80:, host:"8080"```
- and if you want to connect your VM with your Network IP address use this code
```config.vm.network "forwarded_port", ip: "assigne ip address here"```
- if you want to connect vagrant VM via SSH run ```vagrant ssh``` (if you have mustiple VM then specify via VM hostname)
- All set now you can control you VM via SSH.

- Use ```Halt``` command to shut down machine (For mustiple machine use ```halt [VM-Name]```
