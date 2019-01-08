# Project setup
### create a Vagrantfile
Create a root directory for your project.
```sh
$ mkdir vagrant_demo
```
Change to root directory
```sh
$ cd vagrant_demo
```
### Initializing the directory for usage with Vagrant
```sh
$ vagrant init
```
This will place a Vagrantfile in your current directory.

### Initializing and describing the kind of machine
```sh
$ vagrant init ubuntu/trusty64
```
You can also run vagrant init in a pre-existing directory to set up Vagrant for an existing project.
#### Tip:
Boxes are broken down into two parts - the username and the box name - separated by a slash.
The username is "ubuntu", and the box is "precise64" in the above command.

### Boxes
Vagrant uses a base image to quickly clone a virtual machine. These base images are known as "boxes" in Vagrant.

If you have not added a box yet, you can do so now
```sh
$ vagrant box add ubuntu/trusty64
```
This will download the box named "ubuntu/trusty64" from Vagrant Cloud box catalog.

you can also add boxes from a local file, custom URL, etc.

#### Using a Box
The box has been added to Vagrant, we need to configure our project to use it as a base. Open the Vagrantfile and change the contents to the following:
```sh
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
end
```
The "ubuntu/trusty64" in this case must match the name you used to add the box above. This is how Vagrant knows what box to use. If the box was not added before, Vagrant will automatically download and add the box when it is run.

You may also specify the URL to a box directly using config.vm.box_url:
```sh
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://vagrantcloud.com/ubuntu/trusty64"
end
```
#### Up And SSH
To boot your first Vagrant environment.
```sh
$ vagrant up
```
SSH into the machine:
```sh
$ vagrant ssh
```
The SSH session can be terminated with CTRL+D.
```sh
$ vagrant@trusty64:~$ logout
Connection to 127.0.0.1 closed.
```
#### Synced Folders
#### Provisioning
#### Networking
#### Share
#### Teardown
#### Rebuild
#### Providers
