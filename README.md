# Minimal RSP and RSC Installations on VirtualBox VMs

This directory contains everything you need to run two virtual machines, one for RStudio Server Pro and one for RStudio Connect. Virtualization is provided on VirtualBox, the machines are managed through Vagrant, and provisioning is handled with Ansible.

### First

- [Install VirtualBox](https://www.virtualbox.org/)
- [Install Vagrant](https://www.vagrantup.com/downloads.html)
- [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-the-control-machine): `pip install ansible`

### Download CentOS 7 Box

Retrieve a pre-built [CentOS image from Vagrant Cloud](https://app.vagrantup.com/centos/boxes/7):

```
vagrant box add centos/7
```

### Run

From this directory:

- To boot all machines: `vagrant up`
- To stop all machines: `vagrant halt`

Optional:
- Boot up just the RStudio Server Pro machine: `vagrant up rsp`
- Boot up just the RStudio Connect machine: `vagrant up rsc`


### Access

- To SSH into RStudio Server Pro: `vagrant ssh rsp`
- To SSH into RStudio Connect: `vagrant ssh rsc`

The machines need to networked together, or else you wont be able to push-button publish from RSP to RSC. To that end, vagrant private networking is configured to use ip addresses 10.0.0.10 and 10.0.0.11. These addresses can be changed/adjusted as needed in the Vagrantfile.

The RStudio Server IDE will be available at `10.0.0.10:8787`, user: `rstudio` password: `rstudio`. The RStudio Connect Server will be available at `10.0.0.11:3939`, sign-in to create a demo admin account.


### Future Improvements

No additional R packages are installed by default. I might look into creating my own Vagrant box image distribution with R and common packages pre-installed. This would significantly speed up the launch process, but would likely be a pain to maintain (versions).

- Options to use Ubuntu boxes instead of CentOS
- Document options and recs for increased memory on the VM(s) 
