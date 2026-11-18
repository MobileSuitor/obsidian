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
			- 