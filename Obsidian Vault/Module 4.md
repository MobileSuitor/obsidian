<u>Objectives</u>
1. Describe different threat intelligence sources
2. List the steps for securing an endpoint
3. Explain how to create and deploy SecDevOps

------

- **Threat Intelligence Sources**
	- *Key Risk Indicators* (KRI) - data gleaned from monitoring networking environments is used to create a database of Key Risk Indicators. A KRI is a metric of the upper and lower bounds of specific indicators of normal network activity. May include total network logs per second, number of failed remote logins, etc. A KRI that exceeds its normal bounds could be (not always) an *Indicator of Compromise* (IOC)
	- *Categories of Sources*
		- **Open Source Info** - AKA OSINT, this information is collected and disseminated through public info sharing centers. Key concerns of these sharing centers are Privacy (sharing proprietary info) and Speed (info needs to be distributed as fast as possible)
		- **Closed Source Info** - proprietary, typically use private info sharing centers that restrict both access to data and participation
	- *Sources of Threat Intelligence*
		- **Vulnerability Databases** - repository of known vulnerabilities and information as to how they have been exploited
		- **Threat Maps** - illustrates cyberthreats overlaid on a diagrammatic representation of a geographical area
		- **File and Code Repositories** - Victims of an attack can upload malicious files and software code that can then be examined by others to learn more about the attacks
		- **Dark Web** - some security professionals use the dark web on a limited basis to look for signs that info critical to an enterprise is being sought out or sold
- **Securing Endpoint Computers**
	- *Confirm Boot Integrity* - confirming the computer has started without any malicious activity taking place. Boot security involves validating that each element used in each step of the boot process has not been modified. This *chain of trust* starts with the hardware, as it cannot be modified like software (*hardware root of trust*). Some important techniques:
		- **Secure Boot** - each firmware and software executable at boot time must be verified as having prior approval
		- **Trusted Boot** - Windows OS checks the integrity of every component of boot process before loading it, takes over where Secure Boot leaves off by validating the Windows 10 software before loading it
	- *Protect Endpoints* - can be done through software installed on the endpoint, such as antivirus, antimalware, browser protections, etc.
		- **Antivirus** - examines a computer for <u>file-based</u> virus infections as well as monitor activity and scan new documents that might contain a virus
		- **Antimalware** - 