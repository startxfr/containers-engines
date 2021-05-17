# Openshift engine

Documentation and installation guide to install openshift tools under
a RHEL 8 environement.

## Requirements

- Having a basic knowledge of linux command line interface
- Having access to your system environment (see [system install](../system)
  if you don't already have a compliant system)

## Physical infrastructure

Physical infrastructure installation of S2I runtime mean you must be logged to a console
in your system. (see [provision physical OS](../system#physical-infrastructure)))

### Pre installation

*Openshift runtime has no pre-installation tasks.*

### Installation

*Openshift runtime has no installation tasks.*

### Post installation

*Openshift runtime has no post-installation tasks.*

### Check installation

*Openshift runtime has no check-installation tasks.*

## Virtual infrastructure

Virtual infrastructure installation of S2I runtime mean you must be logged to a
console in your system. (see [provision virtual OS](../system#virtual-infrastructure))

### Pre installation

*Openshift runtime has no pre-installation tasks.*

### Installation

*Openshift runtime has no installation tasks.*

### Post installation

*Openshift runtime has no post-installation tasks.*

### Check installation

*Openshift runtime has no check-installation tasks.*

## AWS infrastructure

We recommand using the [sxcm cluster manager](https://sxcm.readthedocs.io) to rpivision and manager you Openshift cluster lifecycle (day one and two) into an AWS infrastructure (public). This is only available for Openshift 4 deployment. OCP 3 should follow the physical method.

### Pre installation

Follow the [sxcm installation guide](https://sxcm.readthedocs.io/en/latest/1-installation/) to learn the requirements and how to install the scm command line.

In short, you should run

```bash
# Install the sxcm command line
source <(curl -s https://raw.githubusercontent.com/startxfr/sxcm/stable/installer)
# Setup you personal environment , including gitops repository aws and redhat credentials
sxcm setup
```

### Installation

Follow the [sxcm cluster lifecycle](https://sxcm.readthedocs.io/en/latest/1-installation/) to learn how to create, configure and deploy your cluster.

In short, you should run

```bash
# Create the mycluster cluster based on the micro profile
sxcm create mycluster micro
# Deploy the current active cluster
sxcm deploy
```

### Post installation

Following the [sxcm cluster lifecycle](https://sxcm.readthedocs.io/en/latest/1-installation/) documentation, you can access your cluster after the full procedure is done.

```bash
# connect to the active cluster
sxcm connect
# Get info (including creds) of the active cluster
sxcm info
```

### Check installation

```bash
# connect to the active cluster
sxcm connect
# Get vital informations about the cluster
oc get nodes
oc get clusteroperator
oc get clusterversion
```

## Test runtime

```bash
# run an application
oc project test-ocp
oc new-app --docker-image quay.io/startx/apache:latest --name website-test -n test-ocp
oc get all -n test-ocp
```
