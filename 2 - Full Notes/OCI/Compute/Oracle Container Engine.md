**Date**: 2025-09-26 16:27

**Topics**: [[oci]] [[compute]]

**Category**: #oci #compute

## Notes :

#### VM V/S Container

![[Pasted image 20250926162816.png]]

#### Disadvantages of VM's :

![[Pasted image 20250926162932.png]]


#### Container Orchestration

- **Kubernetes**: Used to orchestrate containers — handles scaling, networking, communication, load balancing, and scheduling across nodes.
- **Docker**: Used to build container images and run containers.

![[Pasted image 20250926163254.png]]

#### Container Engine for Kubernetes (OKE)

##### Components in a Cluster :

![[Pasted image 20250926163535.png]]

###### ==Worker Nodes==
**Node**  
- A single machine (VM or physical) where workloads run.
**Pod**  
- The smallest deployable unit. It can contain one or more containers (usually one app per pod).
**Node Pool**  
- A group of worker nodes with the same configuration. Helps in scaling and managing nodes efficiently.

#### Oracle Functions ( Similar to AWS Lamda Function)

![[Pasted image 20250926164442.png]]

## References :
