<u>Objectives</u>
1. List the different types of network security appliances and how they can be used
2. Describe network security technologies

------------

- **Security Appliances**
	- can include firewalls, proxy servers, deception instruments,  intrusion detection and prevention systems, and network hardware security modules
	- *Firewalls* - hardware or software that is designed to limit the spread of malware. Uses bidirectional inspection to examine both outgoing and incoming network packets, allowing approved packets to pass through but can take different actions when detecting a suspicious packet. These actions are based on specific criteria, or **rules**, which can contain the following criteria:
		- **Rules Parameters**
			- Source address - location of the origination of the packet
			- Destination address - address the connection is attempting to reach
			- Source port - TCP/IP port number used to send packets
			- Destination port - the port on the remote computer or device that the packets will use
			- Protocol - defines the network protocol used
			- Direction - direction of traffic for packet
			- Priority - determines the order in which the rule is applied
			- Time - rules can be set to be active only during a scheduled time
			- Context - a rule can be created that is unique for specific circumstances
			- Action - indicates what the firewall should do when conditions of rule are met
		- **Firewall Categories**
			- *Stateful vs Stateless* - ==🟣Stateless packet filtering== looks at a packet and permits or denies it based solely on the firewall rules. ==🟣Stateful packet filtering== uses both the firewall rules and the state of the connection (did the internal device request this packet?)
			- *Open source vs Proprietary* - freely available firewalls versus firewalls owned by an entity that has an exclusive right to them
			- *Hardware vs Software* - A ==🟣software firewall== runs as a program or service on a device, such as a computer or router. ==🟣Hardware firewalls== are specialized devices that inspect traffic. These tend to have more features but are more expensive and can require more effort to configure and manage
			- *Host vs Appliance vs Virtual* - A ==🟣host based firewall== is a software firewall that runs on and protects a single endpoint device. An ==🟣appliance firewall== is typically a separate hardware device designed to protect an entire network. A ==🟣virtual firewall== is one that runs in the cloud, designed for public cloud environments where deploying an appliance firewall would be difficult or even impossible
		- **Specialized Firewall Appliances**
			- *Web application firewall (WAT)* - looks at the applications using HTTP, can block specific websites or attacks that attempt to exploit known vulnerabilities in specific client software and can even block XSS and SQL injection attacks
			- *Network address translation (NAT) gateway* - NAT is a technique that allows private IP addresses to be used on the public Internet. As a packet leaves the network, NAT removes the private IP address from the sender's packet and replaces it with a public one and records the substitution. A ==🟣NAT gateway== is a cloud-based technology that performs NAT translations for cloud services and masks the IP addresses of internal devices
			- *Next generation firewall (NGFW)* - can filter packets based on applications, can detect applications using deep packet inspection, can also perform URL filtering and intrusion prevention services
			- *Unified threat management (UTM)* - device that combines several security functions, including packet filtering, antispam, antiphishing, antispyware, encryption, intrusion protection, and web filtering
	- *Proxy Servers* - devices that act as substitutes on behalf of the primary device.
		- **Forward Proxy** - a computer or application that intercepts user requests from the internal secure network and then processes the requests on behalf of the user
		- **Reverse Proxy** - routes requests coming from an external network