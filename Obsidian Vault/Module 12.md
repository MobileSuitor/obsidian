<u>Objectives</u>
1. Describe the different types of authentication credentials
2. Explain the different attacks on authentication
3. Describe how to implement authentication security solutions
----------

- **Types of Authentication Credentials**
	- *Passwords*
		- weakness of passwords centers on human memory due to length and complexity of passwords, number of unique passwords for different accounts, and password policies forcing password changes
		- **Attack Methods**
			- *Spraying* - uses one or a small number of commonly used passwords when trying to log in to several different user accounts
			- *Brute Force* - every possible combination of letters, numbers, and characters is combined to attempt to determine the user's password
			- *Rule Attack* - conducts a statistical analysis on stolen passwords, which is used to create a mask of the format of the candidate password
			- *Dictionary Attack* - creates encrypted versions of common dictionary words and compares them against those in a stolen password file
			- *Rainbow Tables* - large pregenerated data sets of candidate digests. Significant time investment to create, but can be used repeatedly for attacks and drastically cuts down on the time and memory needed by the attacking machine
	- *Smartphones and Security Keys*
		- authentication credentials based on the approved user having a specific item in their possession. Items are typically specialized devices, smartphones, and security keys
		- **Specialized Devices**
			- *Smart Cards* - card that contains information used as part of the authentication process
			- *Windowed Tokens* - small device with a windowed display, usually displaying a one-time password
		- **Smartphones** - often used for authentication due to their ubiquity. Authentication is typically done through a phone call, SMS text message, or authentication app
		- **Security Keys** - hardware device inserted into a computer port that contains all the necessary cryptographic information to authenticate the user
	- *Biometrics*
		- authentication that involves physiological biometrics and cognitive biometrics
		- **Physiological Biometrics**
			- relating to the way in which a body part functions
			- retinal scanners, fingerprints, vein images, gait, voice recognition, iris scanners, facial recognition
		- **Cognitive Biometrics**
			- related to the perception, thought process, and understanding of the user, AKA knowledge-based authentication
		- **Behavioral Biometrics**
			- based on actions that the user is uniquely qualified to perform
			- keystroke dynamics (unique typing rhythm)
- **Authentication Solutions**
	- *Password Security*
		- **Protecting Digests** - additional actions to be taken to protect the contents of digests beyond just securing servers to prevent theft
			- *Salts* - a random string added to a hash algorithm for enhanced security. Makes brute force and dictionary attacks more difficult
			- *Key Stretching* - using a password hashing algorithm that requires significantly more time than standard hashing algorithms to create the digest. Slows down the entire cracking process
		- **Managing Passwords** - virtually impossible for human memory to store long, complex, secure passwords for all accounts. Better suited for specialized technology
			- *Password Vaults* - secure repository for password storage, AKA password manager
				- ***Password Generators*** - web browser extensions that generate passwords based on a master password entered by the user
				- ***Online Vaults*** - also uses web browser extension, retrieves password from central online repository
				- ***Password Management Applications*** - passwords stored locally on a program, protected by one strong master password
			- *Password Keys* - hardware device used to store passwords
	- *Secure Authentication Technologies*
		- **Single Sign-On (SSO)** - using one authentication credential to access multiple accounts or applications
		- **Authentication Services** 
			- *RADIUS* - Remote Authentication Dial-In User Service, industry standard authentication service with widespread support across nearly all vendors of networking equipment
			- *Kerberos* - developed by MIT in the 80s, used to verify the identity of networked users. Users are issued tickets by a Kerberos authentication server with information linking it to the user. This ticket is presented to the network for a service, which examines the ticket to verify identity
			- *TACACS+* - Terminal Access Control Access Control System+, commonly used on UNIX servers, forwards user authentication information to a centralized server
			- *Directory Service* - database stored on the network itself that contains information about users and network devices. Also keeps track of all resources on the network and a user's privileges to those resources
			- *SAML* - Security Assertion Markup Language, XML standard that allows secure web domains to exchange user authentication and authorization data
	