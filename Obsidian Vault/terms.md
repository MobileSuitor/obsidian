<u>Shell</u>
	- program that takes input from the keyboard and passes commands to OS to perform function
	- 'getting a shell' - exploit where attacker gains shell access and can run commands. May be obtained by exploiting a web app or network/service vulnerability, or obtaining credentials > remote login 
	- Shell Connections:
		- **reverse shell** - initiates a connection back to a 'listener' on an attack box
		- **bind shell** - binds to a specific port on the target host and waits for a connection from an attack box
		- **web shell** - runs OS commands via browser, typically not interactive or semi-interactive. Can also be used to run single commands (i.e. leveraging file upload vuln and uploading PHP script)

<u>Port</u>
	- a 'window' or 'door' on a remote system where network connections begin and end. Software-based and managed by host OS. Allow computers to differentiate traffic types (SSH flows to a different port than web requests)
	- some have default configurations, i.e. HTTPS messages go to port 443, while other applications can run on non-standard ports (my media server on 8086)
	- Categories of Ports:
		- **Transmission Control Protocol (TCP)** - connection oriented, meaning that a connection between a client and a server must be established before data can be sent. The server must be in a listening state awaiting connection requests from clients
		- **User Datagram Protocol (UDP)** - connectionless communication model. There is no 'handshake', introduces some unreliability since there is no guarantee of data delivery. Useful when error correction/checking is either not needed or is handled by application itself. UDP can be suitable for applications running time-sensitive tasks since dropping packets is faster than waiting for delayed packets due to retransmission.
	- Examples of TCP and UDP ports:
		- Port 20/21 (TCP) - FCP protocol
		- Port 22 (TCP) - SSH protocol
		- Port 23 (TCP) - Telnet protocol
		- Port 25 (TCP) - SMTP protocol
		- Port 80 (TCP) - HTTP protocol
		- Port 88 (TCP/UDP) - Kerberos protocol
		- Port 161 (TCP/UDP) - SNMP protocol
		- Port 389 (TCP/UDP) - LDAP protocol
		- Port 443 (TCP) - SSL/TLS (HTTPS) protocol
		- Port 445 (TCP) - SMB protocol
		- Port 3389 (TCP) - RDP protocol
		- https://www.stationx.net/common-ports-cheat-sheet/
		- https://web.archive.org/web/20240315102711/https://packetlife.net/media/library/23/common-ports.pdf

<u>Web Server</u>
	- application that runs on the back-end server which handles all HTTP traffic from client-side browser, routes it to requests destination pages, and finally responds to client-side browser
	- usually run on TCP ports 80 and 443
	- web applications can provide a vast attack surface due to being open for public interaction
	- OWASP top 10 vulnerabilities:
		1. **Broken Access Control** - restrictions are not appropriately implemented to prevent users from accessing other accounts, viewing sensitive data, modifying data, etc.
		2. **Cryptographic Failures** - failures related to cryptography which often lead to sensitive data exposure or system compromise
		3. **Injection** - user-supplied data is not validated, filtered, or sanitized by application. Examples: SQL injection, command injection, LDAP injection, etc.
		4. **Insecure Design** - application is not designed with security in mind
		5. **Security Misconfiguration** - missing appropriate security hardening across any part of the application stack, insecure default configurations, open cloud storage, verbose error messages which disclose too much info
		6. **Vulnerable and Outdated Components** - using components (both client and server side) that are vulnerable, unsupported, or out of date.
		7. **Identification and Authentication Failures** - authentication related attacks that target user's identity, authentication, and session management
		8. **Software and Data Integrity Failures** - relate to code and infrastructure that does not protect against integrity violations. Example may be an application that relies on plugins, libraries, or modules from untrusted sources, repositories, and content delivery networks (CDNs).
		9. **Security Logging and Monitoring Failures** - improper or absent logging and monitoring that fail to detect, deescalate, or respond to active breaches.
		10. **Server-Side Request Forgery** - SSRF flaws occur whenever a web application is fetching a remote resource without validating the user-supplied URL. It allows an attacker to coerce the application to send a crafted request to an unexpected destination, even when protected by a firewall, VPN, or another type of access control list (ACL).

<u>Enumeration</u>
	- active reconnaissance process where an attacker systematically queries a target system to extract detailed information
	- goal is to map infrastructure and identify weaknesses such as open ports, usernames, software versions, and network shares
