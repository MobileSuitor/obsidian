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
	5. Logged in and renamed computer to DC01, set static IP ==192.168.50.10== through Server Manager > Ethernet > Network Adapter > Properties > IPv4 Properties, also set mask 255.255.255.0 and gateway 192.168.50.1, DNS 8.8.8.8 for now (change later after DC promotion)
	6. took snapshot - *Clean Install pre-AD*
- **Installing the AD DS Role**
	1. In Server Manager go to Manage > Add Roles and Features. Selected Role-based or feature-based installation, selected DC01, selected Active Directory Domain Services role
		- **Note:** PowerShell can do the above step in one line! Use: 
		==Install-WindowsFeature AD-Domain-Services -IncludeManagementTools==
- **Promoting to Domain Controller**
	1. Yellow flag in Server Manager > selected Promote this server to a domain controller
	2. Selected Add a new forest with root domain name ad.lab.com
	3. Kept functional levels at Windows Server 2016, checked DNS server and Global Catalog. Set DRSM password: Passw0rd
	4. accepted defaults for remaining settings, passed prereqs and installed
- **Post-Promotion Checks**
	1. Change DNS from 8.8.8.8 to 192.158.50.10 
		**Note:** was already pointing to 127.0.0.1, this should be fine but fix if issue
	2. Added DNS forwarder - run ==dnsmgmt.msc==, allows DC to reach the internet so web browsing and updates don't break, used 8.8.8.8
	3. ran ==dcdiag== in PowerShell, most things passed. ran ==nslookip ad.lab.com== but it failed. Issue was reverse lookup timeout, nslookup was trying to find DNS server name with reverse lookup but no reverse zone was configured. Fixed in DNS manager by creating new zone in reverse lookup > primary zone + check store in AD > replication scope defaults > set network ID at 192.168.50. Ran ==ipconfig /registerdns== to update PTR record
