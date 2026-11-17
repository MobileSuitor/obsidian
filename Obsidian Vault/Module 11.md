<u>Objectives</u>
1. Describe the different types of wireless network attacks
2. List the vulnerabilities of WLAN security
3. Explain the solutions for searching a wireless network

------------
- **Wireless Attacks**
	- *Bluetooth Attacks* 
		- Bluetooth is a personal area network (PAN) technology designed for data communication over short distances
		- Bluejacking - attack that sends unsolicited messages to Bluetooth-enabled devices. No data is stolen, so this attack is more annoying than harmful
		- Bluesnarfing - attack that accesses unauthorized information from a wireless device through a Bluetooth connection. Copies emails, calendars, contact lists, pictures and videos
	- *Near Field Communication (NFC) Attacks*
		- NFC is a set of standards used to establish communication between devices in very close proximity (<4cm)
		- risks include data theft by threat actors 'bumping' a portable reader to a user's smartphone in a crowd, intercepting NFC between device and terminal since it is unencrypted (must be close though), or outright stealing a smartphone in order to make purchases
	- *Radio Frequency Identification (RFID) Attacks*
		- RFID is commonly used to transmit information between employee ID badges, inventory tags, book labels, and other paper based tags that can be detected by a proximity reader
		- risks include unauthorized tag access via a rogue RFID reader, fake tags that contain fictitious data when scanned, and eavesdropping
	- *Wireless Local Area Network (WLAN) Attacks*
		- AKA Wi-Fi, several types of attacks are listed below
		- Rogue Access Point - unauthorized AP that allows an attacker to bypass many of the network security configurations and opens the network and its users to attack
		- Evil Twin - AP that is set up by an attacker, designed to mimic an authorized AP
		- Intercepting Wireless Data - attackers can pick up the RF signal from an open or misconfigured AP and read confidential wireless transmissions. If attackers manage to connect to the enterprise wired network through a rogue AP, they could also read, broadcast, and multicast wired network traffic that leaks from the wired network to the wireless network
		- Wireless Denial of Service Attacks - attackers can leverage signals from other devices to disrupt valid wireless transmissions
- **Vulnerabilities of WLAN Security**
	- *Wired Equivalent Privacy* - security protocol designed to ensure that only authorized parties can view transmitted wireless information, accomplished by encrypting the transmissions via a shared secret key known only by the wireless client and the AP
		- several security vulnerabilities:
			- can only use 64/128 bit number to encrypt packets, and length of IV (initialization vector) that precedes it is always 24 bits which limits its strength
			- 24 bit IVs only have 16,777,216 possible values, so IVs would start repeating in less than seven hours if an AP is sending/receiving 700 packets/second, creating a detectable pattern
	- *Wi-Fi Protected Setup* - optional means of configuring security on WLANs. Designed to help users who have little or now knowledge of security to implement security quickly and easily on the WLANs. Uses either a PIN method (PIN on sticker is entered into device to begin security config) or push-button method (physical button is pressed on router to begin security config)
		- PIN method has significant flaws:
			- no lockout limit for entering PINs
			- last PIN character is only  a checksum
			- wireless router reports validity of first and second halves of the PIN separately, so an attacker must break only two short PIN values
	- *MAC Address Filtering* - method for controlling access to WLAN based on the device's MAC address. 
		- several vulnerabilities:
			- MAC addresses are initially exchanged in an encrypted format 
			- managing several MAC addresses can be challenging and demands almost constant attention, not always practical
	- *Wi-Fi Protected Access (WPA)* 
- **Wireless Security Solutions**
	- *Wi-Fi Protected Access 2 (WPA2)* - second gen of WPA security that addresses authentication and encryption on WLANs 
		- ***AES-CCMP Encryption*** - CCMP is the encryption protocol used for WPA2
		- ***IEEE 802.1x Authentication*** - authentication for WPA2 Enterprise model uses the IEEE 802.1x standard, which provides a greater degree of security by implementing port-based authentication. Blocks all traffic on a port-by-port basis until the client is authenticated using credentials stored on an authentication server
	- *Wi-Fi Protected Access 3 (WPA3)* - current gen of WPA with the goal of simplifying security config for users while enhancing network security protections
		- ***Simultaneous Authentication of Equals (SAE)*** - designed to increase security at the time of the handshake when keys are being exchanged
		- WPA3 supports longer 192-bit encryption
		- applies individualized data encryption on public Wi-Fi so that every connection between a client and AP is encrypted with a unique key
		- improved interaction capabilities with IoT devices