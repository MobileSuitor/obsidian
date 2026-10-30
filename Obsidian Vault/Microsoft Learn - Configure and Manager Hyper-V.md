<u>Objectives</u>
1. Describe the functionality and features of Hyper-V on Windows Server
2. Install Hyper-V on Windows Server
3. Describe the options for managing Hyper-V VMs on Windows Server
4. Describe networking features and functionality in Hyper-V on Windows Server
5. Create virtual switches for use with Hyper-V
6. Describe using nested virtualization in Hyper-V

---------
- **Hyper-V Features**
	- *Management and Connectivity* - You can manage your Hyper-V environment with the Hyper-V Manager, Hyper-V module for Windows PowerShell, Virtual Machine Connection (VMConnect), and Windows PowerShell Direct.
	- *Portability* - To make it easier to move or distribute a VM, Hyper-V provides features such as live migration, storage migration, and standard import/export functionality.
	- *Disaster Recovery and Backup* - Hyper-V supports Hyper-V Replica, which creates copies of VMs in other physical locations. These copies can be used to restore VM instances as needed. Other features such as production checkpoints and support for Volume Shadow Copy Service (VSS) facilitate application-consistent backups of VM states.
	- *Security* - Hyper-V supports security features such as Secure Boot and shielded VMs. Secure Boot verifies digital signatures on files during startup to protect against malware. Virtual disks in shielded VMs are encrypted to secure access, and the VMs can only run on specific, protected hosts.
	- *Optimization* - For all supported guest operating systems, Hyper-V includes a set of customized services and drivers called _Integration Services_. These Integration Services include Time Synchronization, Operating System Shutdown, Data Exchange, Heartbeat, Backup, and Guest Services.
- **Installing Hyper-V**
	- *Requirements*
		- A 64-bit processor with second-level address translation (SLAT)
		- A processor with VM Monitor Mode extensions
		- Sufficient memory for the host and guest VMs
		- Intel Virtualization Technology (Intel VT) or AMD Virtualization (AMD-V) enabled
		- Hardware-enforced Data Execution Prevention (DEP) enabled
	- *Installation Methods*
		- Install via **Server Manager** - open Server Manager > Add Roles and Features > select Hyper-V role and Hyper-V Management Tools feature > Install
		- Install via **WAC** - open WAC and select server > locate Hyper-V in Tools list > select Hyper-V Management Tools in Roles and Features area > install
		- Install via **Powershell** - run ==🟣Install-WindowsFeature -Name Hyper-V -ComputerName <computer_name> -IncludeManagementTools -Restart==
			- verify with ==🟣Get-WindowsFeature==
			- **Note** - if you install the Hyper-V server role on a server that contains the Server Core installation option, ==🟣-IncludeManagementTools== parameter will only install the Hyper-V Module for Windows Powershell
- **Hyper-V Manager**
	- Features
		- *Manage remote and local Hyper-V Servers* - Connect to small numbers of Hyper-V hosts, both remote and local, and manage them from a single Hyper-V Manager console over an encrypted HTTPS connection.
		- *Manage Hyper-V VMs* - With Hyper-V Manager, you can perform many management actions such as import, export, connect to, create and delete, or stop and start a VM. You can also modify a VM's virtualized hardware settings, such as Memory, CPU, and Network Adapter.
		- *Enable Hyper-V Replication* - You can enable, disable, and configure Hyper-V Replication on a VM with Hyper-V Manager.
		- *Manage VHDs* - With Hyper-V Manager, you can create, remove, inspect, and configure VHDs and VHD Set files.
		- *Virtual SAN Manager* - Hyper-V Manager includes the Virtual SAN (storage area network) Manager tool. You can use the Virtual SAN Manager tool to create and configure Virtual SANs.
		- *Virtual Switch Manager* - Hyper-V Manager includes the Virtual Switch Manager. With the Virtual Switch Manager you can create vSwitches and configure their connections to external, internal, and private networks.
		- *Manage Checkpoints* - You can enable or disable checkpoint creation for your VMs in Hyper-V Manager, and choose between standard or production checkpoints.
		- *Enable Hyper-V Integration Services* - With Hyper-V Manager, you can enable and disable Hyper-V Integration Services.
		- *Configure Settings for Hyper-V Features* - You can use Hyper-V Manager to configure settings for Hyper-V features. For example, you can select the source and destination computers for live migration or specify a replica server for use with Hyper-V Replica.
		- *Previous Version Support* - When using Hyper-V Manager on Windows Server 2025, you can still manage hosts installed with previous operating systems such as Windows Server 2016, Windows Server 2012, or Windows Server 2012 R2.
		- *Support for WS-Management Protocol* - Hyper-V Manager supports connections to Hyper-V hosts over the Web Services Management Protocol (WS-Management Protocol). This enables Hyper-V Manager to communicate by using the Kerberos protocol NTLM or Credential Security Support Provider (CredSSP). When you use CredSSP, Active Directory Domain Services (AD DS) delegation isn't necessary. This makes it easier to enable remote administration, because WS-Management Protocol communicates either over port 80 or port 443, which are the default open ports.
	- Other methods include managing through PowerShell, PowerShell Direct (PowerShell within a VM), or Windows Admin Center (WAC)
- **Hyper-V Host Best Practices**
	- Provision the host with adequate hardware
	- Deploy VMs on separate disks or Cluster Shared Volumes (CSVs). It's strongly suggested to do so with hard disk drives (HDDs). However, with solid state drives (SSDs), it's possible to have multiple running VMs on the same SSD.
		- minimizes contention by ensuring that any read/write operations required by the VM files don't conflict with read/write operations required by host OS
	- Hyper-V should be the only server role installed on the host server
	- Manage Hyper-V remotely
	- Run Hyper-V by using a Server Core configuration
	- Run the Best Practices Analyzer and use resource metering
	- Use generation 2 VMs if the guest OS supports them
- **Configure Hyper-V Networking**
	- Virtual network adapter types
		- *Legacy network adapter* - emulates and Intel 21140-based PCI Fast Ethernet Adapter. Can be used to perform a network boot for OS installation tasks. Legacy network adapters are available only in generation 1 VMs
		- *Network adapter* - AKA synthetic network adapter. Faster than legacy, but doesn't support network boot for generation 1 VMs. Can be used with both generation 1 and 2 VMs
	- Virtual switch types
		- *Internal* - used to communicate between each of the VMs on a Hyper-V host, and to communicate between VMs and the Hyper-V host
		- *External* - connects VMs to a wired, physical network by binding to a physical network adapter. The management OS can share the adapter when you enable that option in the switch configuration
		- *Private* - facilitates communication between the VMs on the same Hyper-V host. Private switches can't be used to communicate between Hyper-V host and VMs
	- Advanced features
		- *Hyper-V Network Virtualization* - This feature decouples virtual networks from the physical network infrastructure, in much the same way as a hypervisor does for host hardware. It removes the constraints of VLAN and hierarchical IP address assignment from VM provisioning and provides more agility and mobility when managing VMs and tenant workloads. Hyper-V Network Virtualization can be implemented using various components, including the Microsoft Network Controller server role, or network virtualization gateways and load balancers in either Windows Server or System Center Virtual Machine Manager.
		- *Bandwidth Management* - You can use this feature to specify the minimum and maximum bandwidth that Hyper-V allocates to a virtual network adapter. Hyper-V reserves the minimum bandwidth allocation for the adapter even when other adapters for VMs on the same Hyper-V host are functioning at capacity.
		- *DHCP guard* - This feature drops DHCP messages from VMs that are functioning as rogue DHCP servers. This might be necessary in scenarios where you don't have direct control over a VM's configuration and the VM is hosted on a Hyper-V Server you manage.
		- *Router guard* - This feature drops router advertisement and redirection messages from VMs that are configured as unauthorized routers. This feature might be useful when you don't have control over the configuration of VMs hosted on a Hyper-V Server you manage.
		- *Port Mirroring* - You can use this feature to copy incoming and outgoing packets from a network adapter to another VM that you have configured for monitoring.
		- *NIC Teaming* - You can use this feature to add a virtual network adapter to an existing team on the host Hyper-V Server.
		- *Virtual Machine Queue (VMQ)* - This feature requires the host computer to have a network adapter that supports the feature. VMQ uses hardware packet filtering to deliver network traffic directly to a guest. This improves performance because the packet doesn't need to be copied from the host OS to the VM. Only network adapters specific to Hyper-V support this feature.
		- *Single-root I/O virtualization (SR-IOV)* - To use this feature, you must install specific hardware and special drivers on the guest OS. SR-IOV enables multiple VMs to share the same physical Peripheral Component Interconnect Express hardware resources. If sufficient resources aren't available, the virtual switch provides network connectivity. Only network adapters specific to Hyper-V support this feature.
		- *IP Security (IPSec) Task Offloading* - The guest OS and network adapter must provide explicit support for this feature. This feature enables a host's network adapter to perform calculation-intensive, security-association tasks. If sufficient hardware resources aren't available, the guest OS performs these tasks. You can set the maximum number of offloaded security associations from 1 to 4,096. Only network adapters specific to Hyper-V support this feature
- **Nested Virtualization**
	- enables guests to become Hyper-V host, useful for implementing virtual test and development environments that would otherwise require physical hardware to run
	- *Requirements*
		- ![[Pasted image 20261030113434.png]]
	- 