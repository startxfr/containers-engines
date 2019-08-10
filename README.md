# containers-engines

Documentation and installation guides to setup various containers runtimes 
environements including [docker](Docker.md), [docker Enterprise](DockerEE.md), 
[podman](Podman.md), [s2i](S2I.md), [kubernetes](Kubernetes.md) 
and [openshift Enterprise](Openshift.md).


## Purpose

This project is focused on providing a set of guideline and scripts ready to use
to help auditor geting various container environments. Theses runtimes are rady to use
and users can immediatly run various container deployment scenarios using 
simple or advanced features according to the engine you used.


## Audience

- **Developpers** who whant to start building containers with easy to setup environment 
- **Architects** who need to POC CI/CD chains, Software manufacturing workflows as well as
  Private PaaS or CaaS evaluations
- **DevOps teammate** who need to quickly have a simple or complete Contaienr stack
  ready to use for the project
- **Infrastructure administrator** who want to test a new release feature in a sandbox
  environment to perform test and identify impacts and benefits of next releases
  of their containers runtimes.


## Provided engines

Before following one of theses container engine installation guide, read carefully our 
[system guide](System.md#supported-operating-systems) to get informations on 
supported [infrastructure plateforms](System.md) and 
[operating systems](System.md#supported-operating-systems).

| Engine         | Guide                          | Physical infra.                                      | Virtual infra.                                  | AWS infra.
|----------------|--------------------------------|------------------------------------------------------|-------------------------------------------------|-----------------------------------------------
| **Docker**     | [install guide](Docker.md)     | [single host](Docker.md#physical-infrastructure)     | [single host](Docker.md#virtual-infrastructure) | [single host](Docker.md#aws-infrastructure)
| **Podman**     | [install guide](Podman.md)     | [single host](Podman.md#physical-infrastructure)     | [single host](Podman.md#virtual-infrastructure) | [single host](Podman.md#aws-infrastructure)
| **S2I**        | [install guide](S2I.md)        | [single host](S2I.md#physical-infrastructure)        | [single host](S2I.md#virtual-infrastructure)    | [single host](S2I.md#aws-infrastructure)
| **DockerEE**   | [install guide](DockerEE.md)   | [single host](DockerEE.md#physical-infrastructure)   | [cluster](DockerEE.md#virtual-infrastructure)   | [cluster](DockerEE.md#aws-infrastructure)
| **Kubernetes** | [install guide](Kubernetes.md) | [single host](Kubernetes.md#physical-infrastructure) | [cluster](Kubernetes.md#virtual-infrastructure) | [cluster](Kubernetes.md#aws-infrastructure)
| **Openshift**  | [install guide](Openshift.md)  | [single host](Openshift.md#physical-infrastructure)  | [cluster](Openshift.md#virtual-infrastructure)  | [cluster](Openshift.md#aws-infrastructure)


## Terminology

- **Container** : Is a description and filesystem using OS virtualization 
  (shared kernel) and leverage advanced OS features (cgroup, namespace, selinux)
  to provide a portable and flexible way to execute various application runtimes.
- **Container Runtime** : Set of tools used to execute container as defined in the OCI runtime-spec
- **Container image** : Set of files containing a full filesystem ready to be excuted.
  Metadata files embed within the image describe how to execute this container 
  as expected by his creator.
  The files content and structure is defined in the OCI image-spec.
- **Container engine** : Solution allowing to run container using multiple compute nodes
  and providing a clusterized way to run multiples containers in a high-availability 
  environement.
- **OCI** : The Open Container Initiative (OCI) is a Linux Foundation project 
  to define open specifications for Containers images (image-spec) and  runtimes (runtime-spec).


## Authors

This project is developped and maintained by the [startx](https://www.startx.fr) 
dev team. 


## License

This project is licensed under the GPL Version 3 - see the 
[LICENSE.md](https://github.com/startxfr/sxapi-core/tree/dev/docs/LICENSE.md) 
file for more details.
