# containers-engines : System basic


Guideline on how to provision and setup various systems environments on 
[physical OS](#physical-system), [virtual OS](#virtual-system) or 
[AWS OS](#aws-system).


## Physical system


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
yum install -y ansible
```

### Post installation

- Clean yum database and cached packages
```
yum clean all
```

### Check installation

- Test if ansible is working
```
ansible localhost --list-hosts
```


## Virtual system


### Pre installation

- having access to a KVM based virtual hypervisor (RHEV, OVirt) or as simple
hypervisor console such as Machine.

### Installation

- Boot a minimal ISO install image ([centos](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso)
  or [fedora](https://getfedora.org/fr/workstation/download/))
- Execute a minimal installation following the OS installation guide
- After basic installation, log as `root` user and update system packages
```
su root
yum update -y
yum install -y ansible
```

### Post installation

- Clean yum database and cached packages
```
yum clean all
```

### Check installation

- Test if ansible is working
```
ansible localhost --list-hosts
```


## AWS system


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
yum install -y ansible
```

### Post installation

- Clean yum database and cached packages
```
yum clean all
```

### Check installation

- Test if ansible is working
```
ansible localhost --list-hosts
```
