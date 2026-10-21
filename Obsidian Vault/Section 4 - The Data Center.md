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
- **Storage** - in data centers, data storage is usually handled by specialized storage devices rather than storing data on the servers themselves. Redundant storage is critical for data centers.