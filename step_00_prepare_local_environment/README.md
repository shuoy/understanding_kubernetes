Prepare Your Local Environment
==============================

In this tutorial, we are going to use our local machine to learn and play with
Kubernetes first, and [Vagrant](https://www.vagrantup.com) is a great tool for
us to manage local virtual machines.

By using the Vagrant to manage multiple VMs, we will be playing a Kubernetes
cluster on 'a cluster of machines', which will give us more authentic experience
than playing on a single node Kubernetes.



### Install Vagrant on your local machine

In order to run Vagrant, you need:

- Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Install [Vagrant](https://www.vagrantup.com).

This should be all it takes to set up Vagrant.

If you have trouble or not sure about the installation process, please watch the video explaining step-by-step Virtualbox and Vagrant installation at [this great link](https://drupalize.me/videos/installing-vagrant-and-virtualbox?p=1526)

### Test your Vagrant environment is correctly setup

Change your directory to where this README.md file is and use the vagrant command to bring up a VM.

```
# cd step_00_prepare_local_environment
# vagrant up
```

Since the current directory contains a Vagrantfile, which describes what kind of VM that vagrant will bring up, the above commands basically started the VM described in the Vagrantfile. And you should see something like the following:

```
$ vagrant up
Bringing machine 'host0' up with 'virtualbox' provider...
==> host0: Box 'ubuntu/trusty32' could not be found. Attempting to find and install...
    host0: Box Provider: virtualbox
    host0: Box Version: >= 0
==> host0: Loading metadata for box 'ubuntu/trusty32'
    host0: URL: https://atlas.hashicorp.com/ubuntu/trusty32
==> host0: Adding box 'ubuntu/trusty32' (v20151113.0.0) for provider: virtualbox
    host0: Downloading: https://atlas.hashicorp.com/ubuntu/boxes/trusty32/versions/20151113.0.0/providers/virtualbox.box
    ......

     ==> host0: Mounting shared folders...
         host0: /vagrant => /Users/shuoy/prototyping/understanding_kubernetes/step_00_prepare_local_environment    
```

After the above VM booting is finished, you should be able to ssh into the VM and can see the latest Docker engine has been installed -- this means you have successfully used Vagrant to boot a VM. i.e., a final proof that ___your Vagrant/Virtualbox setup is successful.___

```
$vagrant ssh

Welcome to Ubuntu 14.04.3 LTS (GNU/Linux 3.13.0-68-generic i686)

 * Documentation:  https://help.ubuntu.com/

  System information as of Tue Nov 17 17:26:38 UTC 2015

  System load:  0.34              Processes:           77
  Usage of /:   3.1% of 39.34GB   Users logged in:     0
  Memory usage: 40%               IP address for eth0: 10.0.2.15
  Swap usage:   0%

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.


vagrant@host0:~$docker --Version
Docker version 1.9.0, build 76d6bc9
```
