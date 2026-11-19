<u>Objectives</u>
1. Describe Hyper-V Replica, pre-reqs for use, and its high-level architecture and components
2. Describe Hyper-V Replica usage scenarios, available replication settings, and security considerations
3. Configure Hyper-V Replica settings, health monitoring, and failover options
4. Implement Hyper-V Replica
5. Describe extended replication
6. Describe site recovery
7. Implement site recovery

-------------
- **Define Hyper-V Replica**
	- can protect against data loss from site outage by copying a live VM as a replica VM from one location to another
	- involves the main, actively running VM (primary VM) and an offline copy of the primary VM (replica VM)
	- *Prerequisites*
		- supported version of Windows Server with Hyper-V role installed at both primary and replica locations
		- sufficient storage on both hosts to store and run all VMs
		- sufficient storage for log files that contain changes at primary location
		- network connectivity between locations 
		- firewall rules to allow replication between locations (Hyper-V Replica HTTP Listener and Hyper-V Replica HTTPS Listener)
		- authentication certification or AD DS infrastructure requirements
	- [[High-Level Architecture]]
- **Hyper-V Replica Host Scenarios**
	- *Both Hyper-V hosts are standalone servers* - not preferred option, as it includes only disaster recovery and not high availability
	- *Hyper-V host at primary location is a node in a failover cluster, and Hyper-V host at secondary location is on a standalone server* - failover cluster provides high availability for running VMs, replica of VMs available at secondary location
	- *Each Hyper-V host is a node in a different failover cluster* - in the event of disaster at primary location, you can perform a manual failover and continue operations from secondary location
	- *Primary Hyper-V host is a standalone server, secondary Hyper-V host is a node in a failover cluster* - rare configuration, as you typically want high availability at the primary location
- 