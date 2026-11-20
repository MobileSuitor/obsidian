<u>Objectives</u>
1. Understand the function of VM tools
2. Examine other devices that can be virtualized
3. Understand the configuration options for these devices
4. Understand how these devices can be optimized

-------------
- **VM Tools**
	- utilities that are added to VMs to optimize performance and improve use experience
	- added as system services, optimized device drivers, and user processes
	- not mandatory, but vital for good performance
- **Virtualized Devices**
	- *CD/DVD Drives*
		- used primarily for loading software
		- hypervisors control which virtual machine has access to the physical device
	- *Floppy Disks*
		- legacy support for older systems
		- virtual floppy disks can be used to transfer information
	- *Sound Cards*
		- not usually needed for VMs, with the exception of virtual desktops
		- VMs use the sound card of the physical client device, not the virtualization host 
	- *USB Devices*
		- hypervisor redirects USB traffic to the VM that is connected to the device
	- 