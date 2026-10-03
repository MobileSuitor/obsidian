Contained herein shall be the notes and documentation
pertaining to the Active Directory Lab project 

------------------------

<u>10/3/26</u>
Downloaded Windows 11 Enterprise and Windows Server 2022 from Microsoft Evaluation Center, to be set up on individual VMs via VirtualBox. The general plan for this lab is laid out in the following phases:
1. Create VirtualBox NAT Network or Internal Network so VMs can communicate
2. Create Windows Server VM, give it a static IP, install the AD DS role, promote it to a domain controller and set up DNS
3. Create Windows 11 VM, point DNS to domain controller, join domain and log in with a domain account
4. Practice making OUs, users, and security groups. Configure DHCP, set up file shares with permissions
5. Practice managing group policy - password policy, desktop wallpaper, mapped drives, software restrictions, folder redirection, etc.
6. Explore more admin tools - backups, powershell scripts/automation, etc.

- **Creating NAT Network in Virtual Box**
	1. In VirtualBox, go to File > Tools > Network > NAT Networks tab. Created LabNet and set IPv4 prefix to ==192.168.50.0/24==, disabled DHCP to set up on DC later.
- **Creating Windows Server/DC VM**
	1. Config settings
		- user:Administrator | pass:Passw0rd
		- RAM: 4096 MB
		- CPU: 2 cores
		- Disk: 50GB
		- Network: attached adapter 1 to Nat Network > LabNet
	2. Encountered license error during boot. Cause was unattended installation injecting its own info. Disabled unattended installation and proceeded with install
	3. Selected Desktop Experience option during installation for GUI
	4. Select Custom installation and choose drive for installation
	5. Logged in and renamed computer to DC01, set static IP ==192.168.50.10== through Server Manager > Ethernet > Network Adapter > Properties > IPv4 Properties, also set mask 255.255.255.0 and gateway 192.168.50.1, DNS 8.8.8.8 for 
