<u>Objectives</u>
1. Describe the Hyper-V high availability options
2. Describe Hyper-V VMs load balancing
3. Implement Hyper-V VMs live migration
4. Implement Hyper-V VMs storage migration

------------
- **Select High-Availability Options for Hyper-V**
	- *Host Clustering* - utilizes a failover cluster consisting of nodes running the Hyper-V server role. Allows you to configure VMs as highly available clustered resources. Guest OS and its workloads don't have to be cluster-aware
	- *Guest Clustering* - configures failover clustering of Hyper-V VMs instead of physical servers. Essentially has redundant VM instances instead of redundant servers. Application or services intending to be protected must be cluster-aware
	- *Network Load Balancing (NLB)* - Windows Server OS feature. Distributes IP traffic to multiple instances of a TCP/IP based service, such as a web server running on multiple members of the NLB cluster. NLB exposes that service to client applications by using a virtual host name or virtual IP address. From client perspective, the cluster seems to be a single server responding to requests, but each response may originate from a different node in the NLB cluster in reality
- **Implement Hyper-V VM Live Migration**
	- feature that allows you to seamlessly move running VMs from one Hyper-V host to another while maintaining availability of VM workloads
	- enabled and configured using Hyper-V settings in Hyper-V manager
- **Implement Hyper-V VMs Storage Migration**
	- transfers the state of a VM between two Hyper-V hosts
	- can be used to move VM disk files while the corresponding VM is running
	- helps with resolving disk space issues on Hyper-V hosts. If storage is available on another cluster, you can use storage migration to transfer existing VHD files to it without affecting availability of your virtualized workloads