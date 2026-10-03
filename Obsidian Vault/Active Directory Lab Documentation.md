Contained herein shall be the notes and documentation
pertaining to the Active Directory Lab project 

------------------------

<u>10/3/26</u>
Downloaded Windows 11 Enterprise and Windows Server 2022 from Microsoft Evaluation Center, to be set up on individual VMs via VirtualBox. The general plan for this lab is laid out in the following phases:
1. Create VirtualBox NAT Network or Internal Network so VMs can communicate
2. Create Windows Server VM, give it a static IP, install the AD DS role, promote it to a domain controller and set up DNS
3. Create Windows 11 VM, point DNS to domain controller, join domain and log in with a domain account
4. Practice making OUs, users, and security groups. Configure DHCP, set up file shares with permissions
5. Practice managing group policy - passwor
