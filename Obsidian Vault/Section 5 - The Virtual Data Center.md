<u>Objectives</u>
1. Identify the components of a software-defined data center; the hypervisor, management server, management interface
2. Understand the advancements in efficiency server, storage, and network virtualization provides for data centers
3. Awareness of the Proxmox hypervisor and Proxmox VE management interface
4. Understand the functionality of virtualized storage pools and data stores and how they provide scalable storage for VMs
5. Identify the logical components of a virtual network
6. Learn the types of virtual networks
7. Understand virtual data center enablement of cloud
8. Understand the importance of hypervisor security
------------------
<u>Key Terms</u>
1. **KVM** - kernel-based virtual machine; open-source hypervisor technology which is available on Linux OSs
2. **Central Management Server** - server that coordinates and manages servers across a virtual data center
3. **Web-Based Management Interface** - dashboard administrators use to interact with the virtualized data center environment
4. **Virtual Data Center** - data center where physical data center components have been virtualized
5. **Management Layer** - software that acts as the control center for all virtual components and resources across the physical and virtual data center infrastructure
6. **Bridged Network** - type of virtual network where both a VM and its host are connected to the same network by connecting to the host's NIC to the VM's vNIC. VM shares IP with host
7. **Network Address Translation (NAT) Network** - type of virtual network where a VM is connected to a private network on the host called a virtual machine network (VMnet). VM uses host IP address, which is then translated and forwarded to the VM's private IP address on the VMnet
8. **Port Forwarding** - virtual networking feature that enables incoming web traffic to pass through a specific port. This allows IP addresses on a VMnet to be translated and connected to an external network
9. **Host-only Network** - similar to NAT network, but without IP address translation. Restricts access to only the private network, preventing connection to external networks
-----------------------

- **Centralized Management in a Virtual Data Center**
	- central management servers are used to:
		- monitor all hypervisor hosts
		- view and manage VMs across multiple systems
		- allocate resources like CPU, RAM, and storage efficiently
		- set up automation, backup, and high-availability policies
- **The Management Interface**
	- determining how resources are allocated or which virtual machines to be ran are tasks that still need to be handled by sysadmins after a type 1 hypervisor is set up
	- direct interaction with each hypervisor host is done using a **local management interface**
- **Proxmox VE**
	- open source platform that combines all three core components of a virtual data center into one system:
		- *KVM-based type 1 hypervisor* - provides foundation for full virtualization
		- *Built-in central management* - includes a distributed cluster-aware management system that allows you to control multiple servers from one unified dashboard, where admins can create VMs, manage networking, assign storage, and monitor system health from a single location
		- *Integrated web-based host interface* - every Proxmox node comes with its own web-based user interface, allowing direct connection to the virtual datacenter without needing additional client software or a complex setup
- **Server Virtualization**
	- *Storage Virtualization*
		- creating virtual storage from physical storage involves transferring physical storage capacity into logical capacity
		- done by creating a partition and using the space on that partition to create a logical drive, also represented as a **LUN (Logical Unit Number)**
		- LUNs are smaller units, which are put into a larger unit called a volume
		- volumes are then turned into a unit called a datastore, which gets virtualized
		- **Datastore File Systems**
			- *ZFS (local)* - Zettabyte File System acts as a block-level storage to store VM disk images and container data
			- *GlusterFS* - cluster or file-level shared network storage that ensures high availability between nodes
			- *CephFS* - distributed file system integrated into Proxmox VE. Uses pooled storage resources of participating nodes to create network arrays. Also provides an interface that allows VMs to access shared storage similar to NAS or SAN solutions
			- *RBD* - Rados Block Device links block-level storage into an array of disks to be used by VMs. RBD can complement CephFS storage by providing virtual disk access to the CephFS interface
		- **Thin Provisioning** - assigns a LUN a ceiling amount of storage, but the storage space actually used grows as data is being written to it. Essentially on-demand storage that allows its unused storage to be distributed to virtual disks that need it at that moment
	- *Network Virtualization*
		- virtual networks shares the router and NIC with the physical network, but its components are virtualized
		- **Virtual Switch** - first layer of a virtual network, links up virtual devices to the virtual network. Allow VMs on the same server host to communicate with each other using the same protocols  that would be used over physical switches
			- *VLANs* - enable single physical LANs to be segmented, so that groups of ports are isolated from one another as if they were on physically different network segments
- **Types of Virtual Networks**
	- *Bridged Network* - both VM and the host it is running on are connected to the same network. Connects a VM to the network using the host computer's Ethernet adapter, host shares IP address with VM
	- *NAT Network* - takes an IP address and translates it into another IP address. VM does not have its own IP address on the external network. NAT translates addresses of VMs in a private network (VMnet) to that of the host machine. When a VM sends a request to access a network resource, the network resource sees it as if the request came from the host machine. The VMnet is able to connect to the public external network using the translated IP addresses enabled by port forwarding
	- *Host-only networking* - creates a private internal network for the VMs to connect to, similar to a NAT network but without IP address translation, so VMs are restricted to the private network only and do not have direct access to the public external network