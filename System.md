# containers-engines : System basic


Guideline on how to provision and setup various systems environments on 
[physical OS](#physical-infrastructure), [virtual OS](#virtual-infrastructure) or 
[AWS OS](#aws-infrastructure).


## Physical infrastructure


### Pre installation

- having access to a physical computer and be available to boot form a USB key.

### Installation

- plug a bootable Linux USB key ([centos](https://wiki.centos.org/HowTos/InstallFromUSBkey)
  or [fedora](https://fedoraproject.org/wiki/How_to_create_and_use_Live_USB/fr))
- Execute a minimal installation following the OS installation guide
- After basic installation, log as `root` user and update system packages
```
su root
yum update -y
yum install -y ansible git
git clone https://github.com/startxfr/containers-engines.git
cd containers-engines/resources/ansible
ansible-playbook playbooks/system/pre-install.yml
```

### Installation

- Execute the installation playbook to get an updated system with basic tools
  installed.
```
ansible-playbook playbooks/system/install.yml
```

### Post installation

- Execute the post-installation playbook to get an updated system with basic tools
  installed.
```
ansible-playbook playbooks/system/post-install.yml
```

### Check installation

- Execute the check playbook to get informations about your installation success.
```
ansible-playbook playbooks/system/check.yml
```


## Virtual infrastructure


### Pre installation

- having access to a KVM based virtual hypervisor (RHEV, OVirt, QEMU) or 
  Virtualbox.
- Boot a minimal ISO install image ([centos](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso)
  or [fedora](https://getfedora.org/fr/workstation/download/))
- Execute a minimal installation following the OS installation guide
- After basic installation, log as `root` user and update system packages
```
su root
yum update -y
yum install -y ansible git
git clone https://github.com/startxfr/containers-engines.git
cd containers-engines/resources/ansible
ansible-playbook playbooks/system/pre-install.yml
```

### Installation

- Execute the installation playbook to get an updated system with basic tools
  installed.
```
ansible-playbook playbooks/system/install.yml
```

### Post installation

- Execute the post-installation playbook to get an updated system with basic tools
  installed.
```
ansible-playbook playbooks/system/post-install.yml
```

### Check installation

- Execute the check playbook to get informations about your installation success.
```
ansible-playbook playbooks/system/check.yml
```


## AWS infrastructure


### Pre installation

- having access to an AWS account with sufficient credit provisionned.

### Installation

- Login to your [AWS console](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin)
  and select the appropriate region you wan't to deploy  your system to.
- Under the `service` menu, select `EC2`, then select `create instance`
- ...
- ...
- After basic installation, log as `root` user and update system packages
```
su root
yum update -y
yum install -y ansible git
git clone https://github.com/startxfr/containers-engines.git
cd containers-engines/resources/ansible
ansible-playbook playbooks/system/pre-install.yml
```

### Installation

- Execute the installation playbook to get an updated system with basic tools
  installed.
```
ansible-playbook playbooks/system/install.yml
```

### Post installation

- Execute the post-installation playbook to get an updated system with basic tools
  installed.
```
ansible-playbook playbooks/system/post-install.yml
```

### Check installation

- Execute the check playbook to get informations about your installation success.
```
ansible-playbook playbooks/system/check.yml
```

## Remove installation

After having installed and tested the various containers runtimes 
environements ([docker](Docker.md), [docker Enterprise](DockerEE.md), 
[podman](Podman.md), [s2i](S2I.md), [kubernetes](Kubernetes.md) 
and [openshift Enterprise](Openshift.md)) you can remove the temporary contents
used by this tools by running the following command :
```
ansible-playbook playbooks/system/uninstall.yml
```
