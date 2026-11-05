<u>Objectives</u>
1. Describe the different types of networking-based attacks
2. List the different network assessment tools
3. Explain how physical security defenses can be used

----------

- **Attacks on Networks**
	- *Interception attacks*
		- Man-in-the-Middle (MITM) - attack that intercepts legitimate communication to eavesdrop on the conversation or impersonate one of the parties
		- Session replay - attack in which the the attacker attempts to impersonate the user by using their session token
		- Man-in-the-Browser (MITB) - attack that intercepts communication between a browser and the underlying computer
	- *Layer 2 attacks* - refers to the OSI model (see [[Figure 8-2]]). Layer 2, the Data Link Layer, is a frequent target of attacks and is responsible for dividing the data into packets along with error detection and correction.
		- Address Resolution Protocol Poisoning - a device using TCP/IP on an Ethernet network can find the MAC address of another endpoint based on the IP address with the ==🟣Address Resolution Protocol (ARP)==. If the IP address for an endpoint is known but the MAC is not, the sending endpoint delivers and ARP packet to all devices on the network that says "if this is your IP address, send me your MAC address". The endpoint with that address sends back a packet with the MAC, and the IP address and corresponding MAC are stored in an ARP cache. Attackers attempt to change the data in the cache so that an IP address points to a different device, known as ==🟣ARP poisoning==
		- Media Access Control Attacks - these attacks target network switches by spoofing MAC addresses. Two common methods:
			- **MAC Cloning** - attackers discover a valid MAC address of a device connected to a switch, spoof the address on their device and send a packet onto the network. The switch changes its MAC address table to reflect the new association of the MAC address with the port to which the attackers' device is connected. All packets intended for the victim's device will now be sent to the attacker's device
			- **MAC Flooding** - attackers flood the memory of a switch with spoofed packets to force it to function like a network hub and broadcast frames to all ports. The attacker can then install software or a hardware device that captures and decodes packets on one client connected to the switch to view all traffic
	- *DNS attacks* - often the focus of attacks, DNS-based attacks substitutes a DNS address so that the computer is silently redirected to a different device. The goal of these attacks is usually URL redirection, but can also be used to negatively affect the domain reputation of a domain
		- **DNS poisoning** - modifies a local lookup table on a device to point to a different domain, such as a malicious DNS server controlled by an attacker
		- **DNS Hijacking** - aims to infect an external DNS server with IP addresses that point to malicious sites, redirecting *all* users accessing the server.
	- *Distributed Denial of Service attacks* - attacks that use several computers to perform synchronized denial of service attacks by flooding servers with bogus requests
	- *Malicious coding and scripting attacks* - attacks that use PowerShell, Visual Basic, Python, and Bash to execute malicious software code and scripts to compromise networks
- **Tools for Assessment and Defense**
	- *Network Reconnaissance and Discovery Tools* - [[Table 8-3]], [[Table 8-4]] (third party)
	- *Linux File Manipulation Tools* - [[Table 8-5]]
	- *Packet Capture and Replay Tools* - collecting and analyzing data packets that cross a network can provide valuable information, and can be used for security to detect unusual behavior, search for unusual domains or IP address endpoints, and discover regular connections to an attacker's command and control server
		- **Wireshark** (GUI packet capture and analysis tool), **Tcpdump** (command line packet analyzer), **Tcpreplay** (tool for editing packets and then replaying the packets back onto the network to observe behavior)
- **Physical Security Controls**
	- I mean what can I even say for this section, it's just fences and shit to keep people out of places. Not going to waste time typing notes for padlocks and razor wire
	- 