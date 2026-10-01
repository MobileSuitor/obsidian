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
			- *Easy to infect* - does not require a specific file on a computer, can be delivered 