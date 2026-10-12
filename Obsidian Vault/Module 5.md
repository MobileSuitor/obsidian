<u>Objectives</u>
1. List and compare the different types of mobile devices and how they are deployed
2. Explain the ways to secure a mobile device
3. Describe the vulnerabilities and protections of embedded and specialized devices
4. Explain the issues surrounding securing specialized devices

--------------

- **Mobile Device Connectivity Methods**
	- *Cellular* - coverage area for a cellular network is divided into cells with transmitters in the middle of these cells that mobile devices use to send and receive signals
	- *Wifi* - AKA Wireless Local Area Network (WLAN), devices within range of a centrally located connection device can send and receive data at varying transmission speeds
	- *Infrared* - instead of using RF as the communication media, some devices can use light. Infrared light shares characteristics with visible light, though infrared ports are rarely used due to limitations with speed 
	- *USB connections* - include standard-size connectors, mini connectors, and micro connectors
- **Enterprise Deployment Models**
	- *Bring your own device (BYOD)* - employees use their own personal mobile devices for business purposes
	- *Corporate owned, personally enabled (COPE)* - employees choose from a selection of company-approved devices
	- *Choose your own device (CYOD)* - employees choose from a limited selection of approved devices, but pay the upfront cost of the device while the business owns the contract
	- *Virtual Desktop Infrastructure (VDI)* - stores sensitive applications and data on a remote server accessed through a smartphone
	- *Corporate owned* - the device is purchased and owned by the enterprise
- **Mobile Device Vulnerabilities**
	- *Physical security* - frequently lost or stolen 
	- *Limited updates* - updates for iOS and Android devices vary considerably, and are typically are only updated for two to three years after their release. Many users keep devices for longer than this period time, which are then vulnerable after they stop receiving updates
	- *Location tracking* - mobile devices using geolocation can be at an increased risk of targeted physical attacks. Attackers can determine where users are located and use that info to follow them and steal the device
	- *Unauthorized recording* - malware that allows attackers to spy on users through their webcam
	- *Connection vulnerabilities* - summarized in the table below
		- [[Table 5-4 Mobile Device Connection Vulnerabilities]]
- **Securing Mobile Devices**
	- *Device Configuration* - includes strong authentication, managing encryption, segmenting storage, and enabling loss or theft services
	- *Mobile Management Tools* - includes mobile device management, mobile application management, mobile content management, and unified endpoint management
		- **Mobile Device Management (MDM)** - allow a device to be managed remotely by an org
		- **Mobile Application Management (MAM)** - while MDM focuses on the device itself, MAM covers the tools and services responsible for distributing and controlling access to apps
		- **Mobile Content Management (MCM)** - Content management supports the creating and subsequent editing and modification of digital content by multiple employees. Can include tracking editing history, version control, indexing, and searching. MCM system is tuned to provide content management to several mobile devices
		- **Unified Endpoint Management (UEM)** - UEM is a group a class of software tools with a single management interface for mobile and computer devices. Can support all the capabilities of MDM, MAM, and MCM
- **Security Issues of Embedded/Specialized Devices**
	- [[Table 5-9 Security Constraints for Embedded Systems and Specialized Devices]]
