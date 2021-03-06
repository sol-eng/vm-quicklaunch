# VM QuickLaunch Playbooks for Vagrant + Ansible + VirtualBox

### First

- [Install VirtualBox](https://www.virtualbox.org/)
- [Install Vagrant](https://www.vagrantup.com/downloads.html)
- [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-the-control-machine): `pip install ansible`

### Currently Available:

- [CentOS 7](/centos-rsp-rsc)
  - RStudio Server Pro
  - RStudio Connect

- [Ubuntu 16.04](/ubuntu-rsp-rsc)
  - RStudio Server Pro
  - RStudio Connect

### Future Improvements

No additional R packages are installed by default. I might look into creating my own Vagrant box image distribution with R and common packages pre-installed. This would significantly speed up the launch process, but would likely be a pain to maintain (versions).

- Document options and recs for increased memory on the VM(s) 
