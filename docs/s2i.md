#  S2I engine


Documentation and installation guide on how to install s2i
tools under a RedHat like distribution environement (see [system guide](../system#supported-operating-systems) 
for more information on supported [infrastructure plateforms](../system) and [operating systems](../system#supported-operating-systems)).


## Requirements

- Having a basic knowledge of linux command line interface
- Having access to your system environment See [system install](../system) 
  if you don't already have a compliant system according to your infrastructure 
  ([physical](../system#physical-infrastructure), [virtual](../system#virtual-infrastructure)
  or [AWS](../system#aws-infrastructure))


## Physical infrastructure 

Physical infrastructure installation of S2I runtime mean you must be logged to a console
in your system. (see [howto provision physical OS](../system#physical-infrastructure))


### Pre installation

- having access to a physical computer installed following the 
  [provision physical OS guide](../system#physical-infrastructure).
- Login as `root` user
- Move under the `/tmp/containers-engines/resources/ansible` directory


### Installation

- Execute the installation playbook by running `ansible-playbook playbooks/s2i/install.yml` command.


### Check installation

- Execute the check playbook by running `ansible-playbook playbooks/s2i/check.yml` command.


## Virtual infrastructure 

Virtual infrastructure installation of S2I runtime mean you must be logged to a 
console in your system. (see [howto provision virtual OS](../system#virtual-infrastructure))


### Pre installation

- having access to a virtual server installed following the 
  [provision virtual OS guide](../system#virtual-infrastructure).
- Login as `root` user
- Move under the `/tmp/containers-engines/resources/ansible` directory


### Installation

- Execute the installation playbook by running `ansible-playbook playbooks/s2i/install.yml` command.


### Check installation

- Execute the check playbook by running `ansible-playbook playbooks/s2i/check.yml` command.


## AWS infrastructure 

AWS infrastructure installation of S2I runtime mean you must be logged to a 
console in your system. (see [howto provision AWS OS](../system#aws-infrastructure))


### Pre installation

- having access to a AWS EC2 instance installed following the 
  [provision AWS OS guide](../system#aws-infrastructure).
- Login as `root` user
- Move under the `/tmp/containers-engines/resources/ansible` directory


### Installation

- Execute the installation playbook by running `ansible-playbook playbooks/s2i/install.yml` command.


### Check installation

- Execute the check playbook by running `ansible-playbook playbooks/s2i/check.yml` command.


## Test runtime

*S2I runtime has no test-runtime tasks.*


## Remove runtime

After having tested this runtimes you can remove it by running the 
following command :
```
ansible-playbook playbooks/s2i/uninstall.yml
```


