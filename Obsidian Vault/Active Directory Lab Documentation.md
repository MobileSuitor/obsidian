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
- **Creating Windows 11 Client VM**
	1. Config settings
		- user:User1 | pass:Passw0rd
		- RAM: 4096
		- CPU: 2 cores
		- Disk: 64GB 
		- Motherboard settings (Windows 11 req): EFI enabled, TPM to v2.0, Secure Boot enabled
		- Display: VRAM 128MB
		- Network: attached adapter 1 to Nat Network > LabNet
	2. error during boot: make sure to hit key when prompted, UEFI looks for boot prompt
	3. renamed PC to CLIENT01. Set static IP ==192.168.50.20==, mask 255.255.255.0, gateway 192.168.50.1. Set DNS server to point at DC (192.168.50.10) and no fallback to prevent using public DNS
	4. took snapshot - *Clean install, pre-domain*
- **Troubleshooting Network Issues Between Client and DC**
	1. Noticed that the client was unable to connect to DC
	2. Checked DC with ==Get-NetConnectionProfile== and saw NetworkCategory was listed as Public
	3. Verified DNS server was pointing to DC static IP
	4. Attempted to restart Network Location Awareness service with ==Restart-Service NlaSvc -Force==, but command timed out due to service hanging
	5. Tried bouncing the adapter and Netlogon service to prompt NLA to re-detect domain using:
		- ==Restart-Service Netlogon==
		- ==Disable-NetAdapter -Name "Ethernet" -Confirm:$false==
		- ==Enable-NetAdapter -Name "Ethernet"==
	6. tested Get-NetConnectionProfile again and saw that NetworkCategory was now DomainAuthenticated. Success!
	7. Ran ==sc.exe config NlaSvc start= delayed-auto== to delay NLA service to prevent it from finishing before AD is set up. Saved new snapshot of DC01

-----------
<u>10/11/2026</u>
Laptop was struggling to run more than two VMs, so I made the decision to migrate this lab to my main desktop, which has 32GB of RAM. This lab and its initial setup will be almost identical to the documentation above. Notable changes include adjusting the static IP range to 10.10.10.0/24 to avoid conflicts with home network that use 192.168.50.0/24 The phases are as follows:
1. Create VirtualBox NAT Network or Internal Network so VMs can communicate
2. Create Windows Server VM, give it a static IP, install the AD DS role, promote it to a domain controller and set up DNS
3. Create Windows 11 VM, point DNS to domain controller, join domain and log in with a domain account
4. Practice making OUs, users, and security groups. Configure DHCP, set up file shares with permissions
5. Practice managing group policy - password policy, desktop wallpaper, mapped drives, software restrictions, folder redirection, etc.
6. Explore more admin tools - backups, powershell scripts/automation, etc.

- **Creating NAT Network in Virtual Box**
	1. In VirtualBox, go to File > Tools > Network > NAT Networks tab. Created LabNet and set IPv4 prefix to ==10.10.10.0/24==, disabled DHCP to set up on DC later
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
	5. Logged in and renamed computer to DC01, set static IP ==10.10.10.10== through Server Manager > Ethernet > Network Adapter > Properties > IPv4 Properties, also set mask 255.255.255.0 and gateway 10.10.10.1, DNS 8.8.8.8 for now (change later after DC promotion)
	6. Check for updates and restart for installation
	7. took snapshot - *Clean Install pre-AD*
- **Installing the AD DS Role**
	1. In Server Manager go to Manage > Add Roles and Features. Selected Role-based or feature-based installation, selected DC01, selected Active Directory Domain Services role
		- **Note:** PowerShell can do the above step in one line! Use: 
		==Install-WindowsFeature AD-Domain-Services -IncludeManagementTools==
- **Promoting to Domain Controller**
	1. Yellow flag in Server Manager > selected Promote this server to a domain controller
	2. Selected Add a new forest with root domain name ad.lab.local
	3. Kept functional levels at Windows Server 2016, checked DNS server and Global Catalog. Set DRSM password: Passw0rd
	4. accepted defaults for remaining settings, passed prereqs and installed
- **Post-Promotion Checks**
	1. Change DNS from 8.8.8.8 to 10.10.10.10 
	2. Added DNS forwarder - run ==dnsmgmt.msc== > right click DC01, Forwarders. Allows DC to reach the internet so web browsing and updates don't break, used 8.8.8.8
	3. ran ==dcdiag== in PowerShell, most things passed. ran ==nslookup ad.lab.local==, succeeded this time
	4. Confirmed \_msdcs folder in DNS manager along with DC zone, lets clients locate DC
	5. Opened Active Directory Users and Computers to look around
	6. created reverse lookup zone in case of timeout problem with nslookup: DNS manager > reverse lookup zones > new zone > primary IPv4 > network ID 10.10.10 > allow secure dynamic updates
	7. Took new snapshot: *AD DS promoted, healthy*
	8. ran ==ipconfig /registerdns==, and ==nslookup 10.10.10.10== > returned domain properly
	9. ran ==Resolve-DnsName ad.lab.local== > returns 10.10.10.10
	10. ran ==Resolve-DnsName google.com== > works from DC, forwarder is functional
	11. rebooted DC01, then ran ==Get-NetConnectionProfile== > network category listed as private, not DomainAuthenticated
		- ==nltest /dsgetdc:ad.lab.local== returns DC01 so AD is healthy
		- ran ==Restart-Service Netlogon==
		- ran ==Disable-NetAdapter -Name "Ethernet" -Confirm:$False== + ==Enable-NetAdapter -Name "Ethernet"== to bounce adapter 
		- checked ==sc.exe qc NlaSvc== to see what dependencies were configured and added DNS with ==sc.exe config NlaSvc depend=DNS==
		- this seemed to be the fix, with DNS as a dependency, NLA can't start until DNS service is up, so the domain is findable by the time NLA checks
		- rebooted a few more times, just to be sure > confirmed working
	12. Took new snapshot: *AD DS promoted, DNS verified*
- **Creating Windows 11 Client VM** **and joining AD**
	1. Config settings
		- user:User1 | pass:Passw0rd
		- RAM: 4096
		- CPU: 2 cores
		- Disk: 80GB 
		- Motherboard settings (Windows 11 req): EFI enabled, TPM to v2.0, Secure Boot enabled
		- Display: VRAM 128MB
		- Network: attached adapter 1 to Nat Network > LabNet
	2. error during boot: make sure to hit key when prompted, UEFI looks for boot prompt
	3. renamed PC to CLIENT01. Set static IP ==10.10.10.20==, mask 255.255.255.0, gateway 10.10.10.1. Set DNS server to point at DC (10.10.10.10) and no fallback to prevent using public DNS
	4. ran updates, rebooted if necessary
	5. took snapshot - *Clean install, pre-domain*
	6. ran the following tests before joining domain (with DC01 running):
		- ==Test-NetConnection 10.10.10.10 -Port 53== > succeeded
		- ==Resolve-DnsName ad.lab.local -Server 10.10.10.10== > succeeded
		- ==Resolve-DnsName google.com -Server 10.10.10.10== > succeeded
	7. health checks passed, joining CLIENT01 to domain:
		- ==Add-Computer -DomainName ad.lab.local -Credential (Get-Credential) -Restart== > run on CLIENT01 <u>as administrator</u>, enter credentials as AD\Administrator and Passw0rd
		- Alternatively, sysdm.cpl > Change > Domain works as well
	8. Sign is as Other User on reboot, credentials AD\User1 or AD\Administrator
		- AD\User1 doesn't work as it is a local account, not a domain account
		- on DC01, ran ==Get-ADUser -Filter \* |  Select-Object Name, SamAccountName, Enabled== to confirm available accounts
		- can use .\User1 as a fallback, tells Windows to use local account database
	9. Create a real domain user for CLIENT01:
		- DC01 > Active Directory Users and Computers > Users > New > User
		- set logon name as User1, set password = Passw0rd! to meet requirements and checked User must change password at next logon. Change to Passw0rd
	10. took snapshot on both VMs - *AD joined*

-------
<u>10/23/2026</u>
Signed up for Azure Education with student credentials from WCC, now I can acquire valid keys for Windows Server 2022 to avoid running into problems later with the evaluation copy trial period running out. Windows 11 Enterprise itself is not listed, but there is a Windows 11 Education key offered, which is essentially the same as Enterprise with some different default settings
