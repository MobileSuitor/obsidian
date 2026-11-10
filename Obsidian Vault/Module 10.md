<u>Objectives</u>
1. Define the cloud and explain how it is used and managed
2. Explain virtualization
3. Describe cloud and virtualization security controls
4. List different secure network protocols

---------

- **Cloud Computing**
	- on-demand infrastructure to a shared pool of configurable computing resources that can be rapidly provisioned and released with minimal management effort or service provider interaction.
		- <u>Advantages</u>
		1. *On-demand self-service* - consumer can make changes, such as increasing or decreasing computing resources, without requiring human interaction from service provider
		2. *Universal client support* - virtually any networked device can access the cloud computing resources
		3. *Invisible resource pooling* - physical and virtual computing resources are pooled together to serve multiple, simultaneous consumers that are dynamically assigned based on needs
		4. *Immediate elasticity* - computing resources can be increased or decreased quickly to meet demands
		5. *Metered services* - fees are based on the computing resources used
	- *Types of Clouds*
		- Public cloud - services and infrastructure are offered to all users with access provided remotely through the internet
		- Community cloud - open only to specific orgs that have common concerns
		- Private cloud - created and maintained on a private network
		- Hybrid cloud - combination of public and private cloud models
	- *Cloud Architecture*
		- Thin client - computer that runs from resources stored on a central cloud server instead of a localized hard drive
		- Transit gateway - Amazon Web Services technology that allows orgs to connect all existing virtual private clouds, physical data centers, remote offices, and remote gateways into a single managed source
		- Serverless infrastructure - cloud infrastructure in which the capacity planning, installation, setup, and management are all invisible to the user because they are handled by the cloud provider
- **Securing Cloud Computing**
	- [[Table 10-4]] - Cloud Security Issues
	- *Cloud Security Controls* - security controls exist to reduce or mitigate the risk to assets. Can be a policy, procedure, technique, method, solution, plan, action, or device. Controls include conducting audits, using regions and zones, implementing secrets management, and enforcing mitigations
		- **Conducting Audits** - a ==🟣cloud security audit== is an independent examination of cloud service controls and their adherence to established standards
		- **Use Regions and Zones** - having several redundant data centers per region, or partitioning applications across multiple zones, creates systems that are more highly available, fault tolerant, and scalable
		- **Implementing Secrets Management** - process that enables strong security and improved management of a microservices-based architecture
		- **Enforce Functional Area Mitigations** - cloud computing has three functional areas: storage, network, and compute
			[[Table 10-6]] - Functional Area Controls
	- *Next Generation Secure Web Gateway (SWG)* - combines several features into a single product. Examines incoming and outgoing traffic, performs basic URL and monitoring in web applications, analyzes received traffic, performs DLP, provides alerts to a monitoring device.
- **Secure Network Protocols**
	- *Simple Network Management Protocol (SNMP)* - used to manage network equipment that is supported by most network equipment manufacturers. Each SNMP managed device must have an agent or SNMP service that listens for commands and executes them
	- *Domain Name System Security Extensions (DNSSEC)* - adds additional resource records (define the data types being used) and message header information (verifies requested data has not been altered in transmission) for improved security
	- *File Transfer Protocol (FTP)* - unsecure TCP/IP protocol for transferring files. Secure variations are *FTP Secure (FTPS)*, which combines FTP and SSL/TLS, and *Secure FTP (SFTP)*, which is an entirely separate protocol that encrypts data
	- *Secure Email Protocols* - two email systems are in use today: Simple Mail Transfer Protocol (SMTP) and Post Office Protocol (POP)
		- **SMTP** - handles outgoing mail (port 25)
		- **POP** - handles incoming mail (port 110)
	- *Lightweight Directory Access Protocol (LDAP)* - directory service that is a simpler subset of the Directory Access Protocol
		- **Directory Service** - database stored on the network itself that contains information about users and network devices