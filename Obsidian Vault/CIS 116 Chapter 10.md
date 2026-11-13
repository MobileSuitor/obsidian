<u>Objectives</u>
1. understand how VMs connect to the physical network and to each other
2. understand the network config options for VMs
3. understand basic virtual network concepts
4. examine network tuning practices for VMs

-------------
- **VM network basics**
	- VMs are isolated from physical resources without being connected via a network connection
	- consolidation places many VMs on a single host that must provide enough network bandwidth for all of the guests
	- the hypervisor manages the network traffic from the VMs to the physical network
- **Virtual Networks**
	- guest OS behaves as it does in a physical server, connecting to a NIC through a driver
	- hypervisor provides an emulator that appears as a NIC to the guest OS
		- has its own driver that connects to the physical NIC
	- hypervisors can manage virtual internal networks with virtual switches
	- VMs connect to virtual switches that are tied to physical NICs
	- *Bridged Network Connection* - each VM has a unique IP address that is recognized and reachable from outside the host, hypervisor manages traffic with virtual switch
- **Network Address Translation**
	- each VM has a unique IP address but is not reachable from outside the host
	- the host translates the address for use on the outside network and routes responses to the correct VM
- **Virtual Network Tuning**
	- network I/O control can guarantee adequate network bandwidth to individual VMs, groups of VMs, or classes of traffic, during high usage and contention
	- tools available from both virtualization vendors and networking vendors that can monitor network traffic
	- best practices developed on physical networks can also apply to virtual ones
	- 