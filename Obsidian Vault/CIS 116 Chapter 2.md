<u>Objectives</u>
	- Describe a hypervisor
	- Understand difference between type 1 and type 2 hypervisors
	- Understand the two roles of a hypervisor
	- Understand the history of today's hypervisors and the commercial market

---------

- **Hypervisor** - software that abstracts hardware resources from virtual machine. Manages all the interactions between a VM and the hardware resources.
	- *Type 1* - runs directly on hardware, more secure and better performance for guests
	- *Type 2* - runs as application on top of OS, leverages OS drivers. Typically worse performance but better for small scale use
	- Roles - abstracting hardware resources from VMs they support, and load balance the utilization of those resources
- **Hypervisor examples**
	- *VMware ESXi* - first commercially available hypervisor (1998) for the x86 platform
	- *Xen* - first released in 2002 as open source project, began as Cambridge University project
	- *Hyper-V* - first released in 2008, similar architecture to Xen; device drivers are part of parent partition