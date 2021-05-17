# containers-engines : Docker


Documentation and installation guide on how to install docker and docker-compose 
tools under a RedHat like distribution environement (see [system guide](System.md#supported-operating-systems) 
for more information on supported [infrastructure plateforms](System.md) and [operating systems](System.md#supported-operating-systems)).


## Requirements

- Having a basic knowledge of linux command line interface
- Having access to your system environment See [system install](System.md) 
  if you don't already have a compliant system according to your infrastructure 
  ([physical](System.md#physical-infrastructure), [virtual](System.md#virtual-infrastructure)
  or [AWS](System.md#aws-infrastructure))


## Physical infrastructure 

Physical infrastructure installation of Docker runtime mean you must be logged to a console
in your system. (see [howto provision physical OS](System.md#physical-infrastructure))


### Pre installation

- having access to a physical computer installed following the 
  [provision physical OS guide](System.md#physical-infrastructure).
- Login as `root` user
- Move under the `/tmp/containers-engines/resources/ansible` directory


### Installation

- Execute the installation playbook by running `ansible-playbook playbooks/docker/install.yml` command.


### Check installation

- Execute the check playbook by running `ansible-playbook playbooks/docker/check.yml` command.


## Virtual infrastructure 

Virtual infrastructure installation of Docker runtime mean you must be logged to a 
console in your system. (see [howto provision virtual OS](System.md#virtual-infrastructure))


### Pre installation

- having access to a virtual server installed following the 
  [provision virtual OS guide](System.md#virtual-infrastructure).
- Login as `root` user
- Move under the `/tmp/containers-engines/resources/ansible` directory


### Installation

- Execute the installation playbook by running `ansible-playbook playbooks/docker/install.yml` command.


### Check installation

- Execute the check playbook by running `ansible-playbook playbooks/docker/check.yml` command.


## AWS infrastructure 

AWS infrastructure installation of Docker runtime mean you must be logged to a 
console in your system. (see [howto provision AWS OS](System.md#aws-infrastructure))


### Pre installation

- having access to a AWS EC2 instance installed following the 
  [provision AWS OS guide](System.md#aws-infrastructure).
- Login as `root` user
- Move under the `/tmp/containers-engines/resources/ansible` directory


### Installation

- Execute the installation playbook by running `ansible-playbook playbooks/docker/install.yml` command.


### Check installation

- Execute the check playbook by running `ansible-playbook playbooks/docker/check.yml` command.


## Test runtime

*Docker runtime has no test-runtime tasks.*


## Remove runtime

After having tested this runtimes you can remove it by running the 
following command :
```
ansible-playbook playbooks/docker/uninstall.yml
```


