<u>Connecting to VPN</u>
- sudo openvpn user.ovpn

<u>Shows accessible networks</u>
- netstat -rn

<u>Nmap commands & scripts</u>
- nmap -sC
	- specifies that nmap scripts should be used to try and obtain detailed info![[Pasted image 20260720151933.png]]
- nmap -sV
	- performs version scan, fingerprints services on target system and IDs service protocol, application name, and version
- nmap -p-
	- scans all 65,535 TCP ports
- smb-os-discovery.nse
	- interacts with SMB service to extract reported OS version

<u>FTP</u>
- ftp -p /ip address\
	- connects to FTP service via command line, can use standard bash commands

<u>smbclient</u>
- -L flag specifies that we want to retrieve a list of available shares on the remote host, -N flag suppresses password prompt![[Pasted image 20260720154147.png|579]]
- -U flag specifies username |  -U /username\

<u>snmpwalk</u>
![[Pasted image 20260720155347.png]]![[Pasted image 20260720155358.png]]
- tools such as onesixtyone (https://github.com/trailofbits/onesixtyone) can be used to brute force community string names using a dictionary file included in the GitHub repo
	- onesixtyone -c dict.txt 10.129.42.254
