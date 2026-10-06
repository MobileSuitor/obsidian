*Objectives*
	- what comprises a VM
	- understand how resources appear in a VM
	- understand how requests move through hypervisor and back again
	- Open Virtualization Format

- Virtual Machine composition
	- set of data files
	- instantiation of a container that runs an application
- Virtual hardware - from the VMs perspective, it is a physical server (*Fidelity*). Virtualization approaches each resource differently
	- vCPUs - scheduled slices on a physical CPU. A physical processor core is roughly equivalent to a vCPU. There is little ability to manage vCPUs aside from adjusting the amount
	- Virtual memory - mapped to physical memory but is managed by the hypervisor. VMs can only see and utilize what has been allocated. Usually the resource that runs out first
	- Virtual networking - VM to VM communication is possible without traversing the physical network. This is the area most apt to be misconfigured
	- Virtual storage - storage is presented to VMs in a number of ways. VMs can "see" the C: drive, but it is actually a file on a much larger storage device
- Open Virtualization Format (OVF)
	- vendor neutral industry standard
	- cross vendor and cross platform
	- used to export and import VMs from one platform to another
	- can bundle VMs into one package using .ova extension