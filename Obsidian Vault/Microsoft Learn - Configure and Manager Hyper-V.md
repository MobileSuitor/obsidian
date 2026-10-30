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
	- 