<u>Objectives</u>
1. Describe settings, configuration, and generation versions available for VMs in Windows Server
2. Identify virtual hard disk (VHD) formats and types
3. Create and configure a VM
4. Determine storage options for VMs
5. Describe shared VHDs and VHD sets
6. Describe host and guest clustering with shared VHDs

---------------------
- **Determining Existing VM Configs**
	- VM config version is determined by version of Hyper-V installed on the host machine at the time of the VM creation
	- PowerShell cmdlet to get versions of VMs stored on host:
		==🟣Get-VM * | Format-Table Name, Version==
	- PowerShell cmdlet to identify VM config versions your Hyper-V host supports:
		==🟣Get-VMHostSupportversion==
	- PowerShell cmdlet to determine default config version for Hyper-V host
		==🟣Get-VMHostSupportedVersion -Default==
- **Updating VM Config Version**
	- PowerShell cmdlet to update VM config version, from Hyper-V host machine:
		==🟣Update-VMVersion \<vmname>==
	- VM config versions cannot be downgraded, only upgraded
- **VM Generation Versions**
	- *Generation 1* - supports the following features:
		![[Pasted image 20261113113106.png]]
	- *Generation 2* - supports the following features:
		![[Pasted image 20261113113138.png]]
	- Demo - creating Generation 1 VM
		1. In Hyper-V manager > New Virtual Machine Wizard > Select Generation 1
		2. Hyper-V manager > Summary tab > note generation in Generation Details
		3. Run cmdlet in PowerShell:
			==🟣get-vm | format-list name, state, Generation, status, cpuusage, memoryassigned, virtualmachinetype, status, version==
			- full list of property values available: ==🟣get-vm | get-member==
- **VHD Formats and Types**
	- VHDs can be created and managed with the following methods:
		- Hyper-V manager console
		- Disk management console
		- ==🟣diskpart== command
		- ==🟣New-VHD== cmdlet
		- Windows Admin Center console
	- *VHD formats*
		- **VHD** - supports virtual disks up to 2,040 GB in size and older Hyper-V versions
		- **VHDX** - supports virtual disks up to 64 TB in size. VHDX file structure helps minimize corruption issues if a host suffers a power outage. Also supports larger block sizes for dynamically expanding VHDs and differencing VHDs (provides increased performance). Enables extending or shrinking disk size while VM is running if the VHDX disk is connected to an SCSI controller
		- **VHD SET** - used for shared VHDs only. Enables backup of VM groups that use shared VHDs. Isn't supported in OSs that are earlier than Windows 10
	- it is possible to convert between VHDX and VHD formats by using Hyper-V manager's edit virtual hard disk wizard or by using the ==🟣Convert-VHD== cmdlet
	- *VHD types*
		![[Pasted image 20261113115512.png]]
- **VM Storage Options**
	- Considerations for VHD file storage:
		- *High-performance connection to storage* - VHD files located on remote storage must have adequate bandwidth and minimal latency
		- *Redundant storage* - fault tolerance, VM should remain operational in the event of a disk failure
		- *High-performance storage* - storage device should have excellent I/O characteristics. Many enterprises use hybrid SSDs in RAID 10 arrays for maximum performance and redundancy
		- *Adequate growth space* 
	- *Fiber Channel support for SANs*
		- uses Hyper-V virtual Fibre Channel adapter to enable access to Fibre Channel storage on SANs
		- must configure Hyper-V host with a Fibre Channel host bus adapter or Fibre Channel over Ethernet network adapter
	- *Storing VMs on SMB 3.0 file shares*
		- recommended bandwidth for network connectivity to SMB file share is 1 Gbps or more
		- be sure to separate network traffic to file shares that contain VM files. Client network traffic shouldn't be on the same VLAN as SMB traffic
- **Shared VHDs vs VHD Sets**
	- *Shared VHD* - VHD created in .vhdx format and connected to the SCSI controllers of multiple VMs. Must be stored on Cluster Shared Volumes (CSVs) or a file server with SMB version 3.0
	- *VHD Sets* - newer alternative for sharing VHDs that addresses the limitations of shared VHDs. Requires Windows Server 2016 or newer
- 