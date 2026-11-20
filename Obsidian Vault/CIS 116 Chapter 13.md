<u>Objectives</u>
1. Examine the need for increased availability in today's information driven world
2. Understand the availability options and strategies in a virtual environment
3. Examine availability in a single VM, in a single virtualization host, and across multiple virtualization hosts

--------
- **Traditional Solutions for Availability**
	- *RAID* - can improve storage availability and performance
	- *Storage Multipathing* - provides multiple paths for storage traffic, works well in virtualization
	- *NIC Teaming (link aggregation)* - multiple network cards linked together for more bandwidth and alternate paths in the event of a NIC failure, works well in virtual environments
	- *Clustering Solutions* - includes Microsoft Cluster Services or Oracle RAC. Can be implemented in VMs or across VMs and physical servers
- **VM Availability**
	- *Enhanced HA* - VM Tools can automatically reboot a failed or frozen VM without intervention
	- *Application HA* - tools that can restart a failed application even though the OS is still running
	- *Storage and Network I/O*- QOS features that ensure critical application workloads receive adequate bandwidth in times of contention to prevent application interruptions
- **High Availability**
	- *Clustering* - two or more physical servers linked together via network and shared storage resources
	- When one physical server fails, all of the VMs on that server are automatically rebooted somewhere else in the cluster
		- need to configure headroom during planning stages
- **Fault Tolerance**
	- Able to withstand virtualization host failures without application interruption
	- Second VM runs in lockstep with primary
		- upon host failure, secondary becomes the primary
		- new secondary created in the cluster
- **Live Migration (vMotion)** 
	- the ability to migrate a running VM from one virtualization host to another without interrupting the user application
	- Maintenance mode
		- evacuates the guests from a host
		- work can be done on the physical host, or even replace the host, without disrupting the guests or their applications
		- planned downtime can occur at any time with no disruption of service
- **Storage Migration**
	- similar to live migration, but in this case the files that compose a VM are moved from one place to another
	- can be used to alleviate disk contention without interrupting the guest
	- can be used to move data to newer storage
- **Protecting Datacenters**
	- leveraging replication solutions can provide current copies of a production site ready to be powered on
	- virtualization eases traditional challenges (network, scaling) with disaster recovery solutions by providing a standard infrastructure
	- future solutions will provide protection for datacenters as an entity and offer movement instead of recovery
		- bandwidth dependent
