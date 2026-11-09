<u>Objectives</u>
1. Understand how VMs connect to storage resources
2. Examine the configuration options for disk storage connecting to VMs
3. Examine tuning practices from storage devices connected to VMs

-----------
- **Connecting Virtual Disks**
	- storage connects to VMs similarly to physical servers but is abstracted from the VMs
	- Many storage best practices used in the physical environment apply very well in the virtual world
		- thin provisioning
		- data deduplication
	- Adequate storage I/O is key for good performance
		- storage connects through specialized storage or standard network interfaces
- **Virtual Storage**
	- VMware architecture
		![[Pasted image 20261106115551.png]]
	- Hypervisor provides storage and network interface emulators that the VM drivers connect to
	- Hypervisor then manages connections and traffic to the physical interfaces
- **Data Deduplication**
	- duplicated entities are replaced by pointers to the original
	- works at byte, block, and file levels
	- can reclaim between 30-90% of storage space
	![[Pasted image 20261106115809.png]]
- **Thin Provisioning**
	- does not pre-allocate disk space when the file system is created like thick provisioning
	- could lead to issues if file systems actually fill the allocated space
	- similar to memory overcommit but for storage
	![[Pasted image 20261106115910.png]]
- **Storage I/O Control**
	- allows QoS policy assigned to a single VM or a group of VMs
	- guarantees appropriate storage throughput in the event of I/O contention to protect business-critical applications
- **Other Topics**
	- *Tiered Storage*
		- storage arrays that have different classes of storage offering multiple levels of service
		- files can be dynamically migrated based on need
	- *Solid-State Disk Drives (SSD)*
		- use solid-state memory instead of spinning platters and moving parts
		- fifty times faster than current disks
	- *Storage Virtualization*
		- one model pools internal server storage from multiple servers into a virtual SAN, which is more cost effective than a separate NAS or SAN