# containers-engines : System basic


Guideline on how to provision and setup various operating systems ([Centos](#centos), [Fedora](#fedora)
or [RHEL](#rhel)) on [physical infrastructure](#physical-infrastructure), 
[virtual infrastructure](#virtual-infrastructure) or [AWS infrastructure](#aws-infrastructure).


## Physical infrastructure


### Pre installation

- having access to a physical computer and be available to boot form a USB key.

### Installation

- plug a bootable Linux USB key ([centos](https://wiki.centos.org/HowTos/InstallFromUSBkey)
  or [fedora](https://fedoraproject.org/wiki/How_to_create_and_use_Live_USB/fr))
- Execute a minimal installation following the OS installation guide
- After basic installation, login as *root* user with a `su root` command
- Install ansible and git by running the `yum install -y ansible git` command
- Clone this git repository using `git clone https://github.com/startxfr/containers-engines.git` command
- Move to the script directory with `cd containers-engines/resources/ansible`
- Execute this pre-installation playbook by running `ansible-playbook playbooks/system/pre-install.yml`

You can use the following script to perform all theses actions in one operation.
```
su root
yum update -y
yum install -y ansible git
git clone https://github.com/startxfr/containers-engines.git
cd containers-engines/resources/ansible
ansible-playbook playbooks/system/pre-install.yml

```

### Installation

- Execute the installation playbook with `ansible-playbook playbooks/system/install.yml`
  command to get an updated system with basic tools installed. 

### Post installation

- Execute the post-installation playbook by running the `ansible-playbook playbooks/system/post-install.yml`
  command

### Check installation

- Execute the check playbook with `ansible-playbook playbooks/system/check.yml` command
  to get informations about your installation success.


## Virtual infrastructure


### Pre installation

- having access to a KVM based virtual hypervisor (RHEV, OVirt, QEMU) or 
  Virtualbox.
- Boot a minimal ISO install image ([centos](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso)
  or [fedora](https://getfedora.org/fr/workstation/download/))
- Execute a minimal installation following the OS installation guide
- After basic installation, login as *root* user with a `su root` command
- Install ansible and git by running the `yum install -y ansible git` command
- Clone this git repository using `git clone https://github.com/startxfr/containers-engines.git` command
- Move to the script directory with `cd containers-engines/resources/ansible`
- Execute this pre-installation playbook by running `ansible-playbook playbooks/system/pre-install.yml`

You can use the following script to perform all theses actions in one operation.
```
su root
yum update -y
yum install -y ansible git
git clone https://github.com/startxfr/containers-engines.git
cd containers-engines/resources/ansible
ansible-playbook playbooks/system/pre-install.yml

```

### Installation

- Execute the installation playbook with `ansible-playbook playbooks/system/install.yml`
  command to get an updated system with basic tools installed. 

### Post installation

- Execute the post-installation playbook by running the `ansible-playbook playbooks/system/post-install.yml`
  command

### Check installation

- Execute the check playbook with `ansible-playbook playbooks/system/check.yml` command
  to get informations about your installation success.


## AWS infrastructure


### Pre installation

- having access to an AWS account with sufficient credit provisionned.

### Installation

- Login to your [AWS console](https://console.aws.amazon.com/console/home?nc2=h_ct&src=header-signin)
  and select the appropriate region you wan't to deploy  your system to.
- Under the `service` menu, select `EC2`, then select `create instance`
- ...
- ...
- After basic installation, login as *root* user with a `su root` command
- Install ansible and git by running the `yum install -y ansible git` command
- Clone this git repository using `git clone https://github.com/startxfr/containers-engines.git` command
- Move to the script directory with `cd containers-engines/resources/ansible`
- Execute this pre-installation playbook by running `ansible-playbook playbooks/system/pre-install.yml`

You can use the following script to perform all theses actions in one operation.
```
su root
yum update -y
yum install -y ansible git
git clone https://github.com/startxfr/containers-engines.git
cd containers-engines/resources/ansible
ansible-playbook playbooks/system/pre-install.yml

```

### Installation

- Execute the installation playbook with `ansible-playbook playbooks/system/install.yml`
  command to get an updated system with basic tools installed. 

### Post installation

- Execute the post-installation playbook by running the `ansible-playbook playbooks/system/post-install.yml`
  command

### Check installation

- Execute the check playbook with `ansible-playbook playbooks/system/check.yml` command
  to get informations about your installation success.


## Supported operating systems


### Centos

#### Supported releases

Centos 7  or Centos 8 releases are both supported for theses guides and our installations scripts.

#### Usefull links

- [Create a bootable Centos USB key](https://wiki.centos.org/HowTos/InstallFromUSBkey)
- [Download Centos7 ISO image](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso)
- [Fast track course on Centos](https://www.freecodecamp.org/news/getting-started-with-centos-15eac7215c99)


### Fedora

#### Supported releases

Fedora Core 29 and 30 releases are both supported for theses guides and our installations scripts.

#### Usefull links

- [Create a bootable Fedora USB key](https://fedoraproject.org/wiki/How_to_create_and_use_Live_USB/fr)
- [Download Center for Fedora ISO image](https://getfedora.org/fr/workstation/download/)
- [What's new in Fedora 30](https://fedoramagazine.org/whats-new-fedora-30-workstation/)


### RHEL

#### Supported releases

RHEL 7  or RHEL 8 releases are both supported for theses guides and our installations scripts.

#### Usefull links

- [Create a bootable RHEL USB key](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/installation_guide/sect-making-usb-media)
- [Download Center for RHEL ISO image](https://access.redhat.com/documentation/fr-fr/red_hat_enterprise_linux/7/html/installation_guide/chap-download-red-hat-enterprise-linux)
- [What's new in RHEL 8](https://www.techrepublic.com/article/whats-new-with-red-hat-enterprise-linux-8-and-red-hat-virtualization/)



## Remove installation

After having installed and tested the various containers runtimes 
environements ([docker](Docker.md), [docker Enterprise](DockerEE.md), 
[podman](Podman.md), [s2i](S2I.md), [kubernetes](Kubernetes.md) 
and [openshift Enterprise](Openshift.md)) you can remove the temporary contents
used by this tools by running the following command :
```
ansible-playbook playbooks/system/uninstall.yml
```
