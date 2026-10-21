<u>Objectives</u>
1. Understand the three core elements of data centers: servers, storage, and networks
2. Awareness of the types of servers and their role in the data center
3. Explore storage technologies and protocols used in data centers
4. Understand the devices and protocols that make up a basic network
5. Knowledge of various data center infrastructure models

-----------------

<u>Key Terms </u>
- **TCP/IP** - network protocol that computers use to transmit data to other devices on a network. The TCP layer segments data into packets, and the IP layer specifies the address of the destination device
- **Parity** - a RAID method that uses a parity bit at the end of a data string as it is being written to disks. This parity data is stored on a dedicated drive that can be used to recover lost data from a failed disk
- **Network Attached Storage (NAS)** - storage method that involves attaching a storage device to a network and giving it its own IP address which allows servers and devices on that network to access the storage 
- **Storage Area Network (SAN)** - a storage method that consists of clustered block level storage devices attached to a high-speed network. Servers on that network can access the data on the storage using specific protocols, such as **iSCSI**

----------

- **Networks** - made up of several hardware components that create a net of communication paths
	- *Router* - a device that can send/receive data across different networks. Once data reaches the desired network, the router sends the data to the right location in the network using IP addresses
	- *Switch* - connects devices to each other within a network. A switch is responsible for creating the communication paths, while a router directs where along the paths the information needs to go
	- *NIC (Network Interface Controller)* - piece of networking hardware built with Ethernet technology that is part of, or attaches to, the motherboard and connects a computer to a network
	- *Ethernet cable* - type of networking cable that physically connects devices such as servers, routers, and switches on a network using Ethernet protocol
	- *Port* - interfaces that serve as the point of communication between the network and a device that is on the network
- **Storage** - in data centers, data storage is usually handled by specialized storage devices rather than storing data on the servers themselves. Redundant storage is critical for data centers
	- *Block level storage* - storage device such as a hard disk drive is identified as a storage volume. Volumes can be treated as an individual device or a block. This gives a server's OS the ability to have access to the raw storage sections. The storage blocks can be modified by an admin, adding more capacity when necessary, which makes block storage fast, flexible, and reliable
	- *File level storage* - file system is directly installed onto a storage device. Volumes appear to have hierarchy of files. Easier to use 
	- *HBA (host bus adapter)* - protocol adapter for servers. Hardware that is plugged into a server, and adapts the server to the storage device protocol. Once the HBA is in place and the cables with the right protocol are used, a storage device can be attached, allowing the DAS to be able to talk to the server. Common protocols for DAS are SCIS, SATA, SAS, and USB
	- *NAS vs SAN* - while NAS is storage that connects to a network, SAN is a network of storage that servers can connect to. NAS manages storage as a file system directly, while SAN does not, and it is the server's OS that is responsible for creating the storage file system (devices that don't have to worry about filing their own data will run faster and be more efficient)
	- *Storage Protocols*
		![[Pasted image 20261021102318.png]]
	- *Storage Provisioning* - process of strategically assigning storage space to servers based on the capacity of the storage devices, availability, and performance requirements
		- **Thick Provisioning** - disk space is strategically pre-allocated to a server or a VM. This means that the logical space provided by partitioning is equal to the amount of actual physical space set aside on the disk. Allows VMs to have guaranteed access to all of its allocated disk space at all times, even if it is not currently using its total capacity. Can lead to resource underutilization