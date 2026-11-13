<u>Objectives</u>
1. Describe settings, configuration, and generation versions available for VMs in Windows Server
2. Identify virtual hard disk (VHD) formats and types
3. Create and configure a VM
4. Determine storage options for VMs
5. Describe shared VHDs and VHD sets
6. Describe host and guest clustering with shared VHDs

---------------------
- **Determining Existing VM configs**
	- VM config version is determined by version of Hyper-V installed on the host machine at the time of the VM creation
	- PowerShell cmdlet to get versions of VMs stored on host:
		==🟣Get-VM * | Format-Table Name, Version==
	- PowerShell cmdlet to identify VM config versions your Hyper-V host supports:
		==🟣Get-VMHostSupportversion==
	- PowerShell cmdlet to determine default config version for Hyper-V host
		==🟣Get-VMHostSupportedVersion -Default==
- 