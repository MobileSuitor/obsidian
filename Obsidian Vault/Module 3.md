<u>Module Objectives</u>
1. Identify the different types of attacks using malware
2. Define application attacks
3. Explain how threat actors use application attacks
4. Define adversarial artificial intelligence attacks

- **Attacks Using Malware**
	- *Ransomware* - prevents a user's endpoint device from properly and fully functioning until a fee is paid. Embeds itself in such a way that it cannot be bypassed, and even rebooting causes the ransomware to launch again
	- *Cryptomalware* - more malicious than ransomware, encrypts all files on the device so that none of them can be opened. Newer variants encrypt all files on any network or attached device connected to the infected computer, including secondary hard disks, USBs, NAS, network servers, and even cloud-based data repos.
	- *Viruses*
		- **File-Based Viruses** - malicious computer code attached to a file, can reproduce itself on the same computer. Each time the infected program is launched or the data file is opened, the virus first unloads a payload to perform a malicious action, then reproduces itself by inserting its code into another file, but only on the same computer. A virus cannot automatically spread to another computer by itself, must rely on actions of users, such as the transfer of infected files to other devices
		- **Fileless Viruses** - take advantages of native services and processes that are part of the OS to avoid detection and carry out its attacks. These native services used in a fileless virus are called *living-off-the-land binaries* (**LOLBins**). Common LOLBins are Powershell, .NET framework, Windows Management Instrumentation (WMI). Since these do not infect a file, they are instead loaded directly in the RAM through a LOLBin and then executed. This offers several advantages over file-based viruses
			- *Easy to infect* - does not require a specific file on a computer, can be delivered through malicious webpages that send a script to pass instructions to a LOLBin
			- *Extensive control* - LOLBins often have extensive control and authority, such as Powershell, that allows them to bypass security features
			- *Persistent* - these viruses often write their script into the Windows Registry, so the script will be launched whenever the computer is restarted or on a set schedule
			- *Difficult to detect* - antivirus will have no file to scan, and LOLBins usage means there is no evidence of other tools being used. Also, LOLBins like Powershell run in a section of system memory that cannot be queried or searched
			- *Difficult to defend against* - full defense means turning off all potential LOLBins, but this would cripple OS function. They also load by default, further complicating defense efforts
	- *Worms* - malicious program that uses a computer network to replicate, AKA network viruses. Exploits vulnerability in application or OS of host and then searches for another on the network with same vulnerability
	- *Bot* - an infected computer placed under the remote control of an attacker, used to launch more attacks. Several bots gathered into a logical computer network is a *botnet*. These are responsible for spam campaigns, spreading malware, ad fraud, and mining crypto. Botnets receive instructions through a <u>command and control</u> structure that indicate which computers to attack and how. Several methods exist:
		- signing in to a bot-herding website where certain information is interpreted as commands
		- signing in to a third-party website, so no affiliation with herder
		- commands sent via blogs, specially coded commands through social media
		- dead drop mechanism - setting up a gmail account and then creating a draft message that is never sent but contains commands that the bot receives when it logs in to gmail and reads the draft. There is no record of the commands since the message is never sent
	- *Spyware* - tracking software that is deployed without the consent or control of the user. Collects info without approval and distributes. Not all spyware is malicious, the book insists, but it is still taking information without consent
	- *Keylogger* - silently captures and stores each keystroke performed by a user. Can be software or a small hardware device. Can also capture what is on the screen and turn on the web camera 
	- *Potentially Unwanted Program (PUP)* - simply software that a user does not want on their computer. More annoying than malicious. Can be installed through the default options of installers, sometimes cannot be removed easily
	- *Trojan* - executable program that masquerades as performing a benign activity but also does something malicious. Remote Access Trojans (RAT) also gives the attacker remote access to the infected computer using specially configured communication protocols
	- *Backdoor* - 