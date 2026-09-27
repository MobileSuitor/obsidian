<u>SSH</u> - runs on port 22 and provides users a secure way to access a computer remotely
	- can be configured with password authentication, or passwordless using public-key authentication using a public/private key pair
	- typically more stable than reverse shell connection
	- can be used as a 'jump host' to enumerate and attack other hosts in the network, transfer tools, set up persistence, etc.
	- can also be used as a way for mapping local ports on the remote machine to the localhost

<u>Netcat</u> - AKA ==ncat/nc==, is a network utility for interacting with TCP/UDP ports
	- primary usage is for connecting to shells
	- can also be used to connect to any listening port and interact with the service running on that port 
	- for example, using netcat on port 22 sends us its banner: ![[Pasted image 20260716165453.png]]
	- the above technique is known as ==Banner Grabbing==, and can help identify what service is running on a particular port.
		- netcat download for Windows: https://nmap.org/download.html

<u>Socat</u> - similar utility to ==ncat==, but with a few extra features that aren't supported by ncat, such as forwarding ports and connecting to serial devices
	- can also be used to upgrade a shell to a fully interactive TTY 
		- https://blog.ropnop.com/upgrading-simple-shells-to-fully-interactive-ttys/#method-2-using-socat
	- a standalone binary (does not require external installations, environment configs, or internet connectivity to run) of socat can be transferred to a system after obtaining remote code execution to get a more stable reverse shell connection

<u>Tmux</u> - AKA terminal multiplexer, is a utility used for expanding a standard Linux terminal's features, such as having multiple windows within one terminal and jumping between them
	- default key to input tmux commands prefix is CTRL + B
		- open a new window: prefix > C
		- switching between windows: prefix > window number (0, 1, etc.)
		- split a window vertically into panes: prefix > SHIFT + %
		- split a window horizontally into panes: prefix > SHIFT + "
		- switching between panes: prefix > LEFT/RIGHT or UP/DOWN
	- useful tool for logging
	- Cheatsheet: https://tmuxcheatsheet.com/
	- Video introduction: https://www.youtube.com/watch?v=Lqehvpe_djs

<u>Vim</u> - text editor that can be used for writing code or editing text files on Linux systems
	- supports extensions and plugins to extend its usage 
	- open a file with: vim /path/to/file
	- commands:![[vim command table]]
	- ==Tip:== any command can be ran multiple times by adding a number before it. '4yw' would copy 4 words instead of one, etc.
	- Cheatsheet: https://vimsheet.com/

<u>Nmap</u> - utility used to scan a designated IP address for available ports
	- without an additional options, scans the 1000 most common ports by default
	- defaults to TCP scan unless requested otherwise
	- SERVICE heading shows the services name that is *typically* mapped to that specific port number. However, default scan will not tell us what is listening on that port, must instruct nmap to interact with service to identify
	- some giveaway ports:
		- port 3389: default port for Remote Desktop Services, indicates Windows machine
		- port 22: SSH service, usually indicates Linux machine, but Windows can configure SSH too
	- https://academy.hackthebox.com/module/details/19

<u>SMB (Server Message Block)</u>
	- Windows protocol that provides many vectors for vertical and lateral movement
	- sensitive data such as credentials can be in network file shares such as this one
		- allows users and admins to share folders and make them accessible remotely by other users
	- some SMB versions may be vulnerable to RCE (Remote Code Execution) exploits, such as EternalBlue

<u>SNMP (Simple Network Management Protocol)</u>
	- provides information and statistics about a router or device
	- manufacturer default community strings of public and private are often unchanged
	- in versions 1 and 2c, access is controlled using a plaintext community string, allowing access if you know the name
	- encryption and authentication were only added in version 3