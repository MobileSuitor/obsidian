<u>Module 1 Introduction to Security</u>
**Terms:**
	Confidentiality: security actions so only authorized parties can view information
	Integrity: data is correct, and has not been altered by unauthorized persons
	Availability: ensure data is accessible to authorized users
	AAA : Authentication Authorization Accounting
**Laws:**
	HIPAA - health insurance portability and accountability act (protect PHI)
	SOX - Sarbanes Oxley, fight corporate corruption
	GLBA - Grahmn, Leach , Bliley Act (Banking / financial policies on customer info)
	PCI-DSS -  payment card industry – data security standards (credit card processing)
	CA DSBNA - California – database security breach notification act 1st State to do this
**People: Hackers (3 flavors)**
	Black hat : illegal hacking for personal gain or malicious acts
	White hat : legal hacking / pen testing with permission from org
	Grey hat: illegal hacking, not for personal gain but to shame org into fixing vulns
**Attackers:** 
	Cybercriminals (money money money) 
	Script kiddies (thrills, fame) 
	Brokers (selling to highest bidders) 
	Insiders (biting the hand that feeds you) 
	Cyberterrorists (panic, disruption, terror) 
	Hactivists (to right perceived wrong) 
	State Sponsored APT (spying, disrupt government, disrupt elections)
**Cyber Kill Chain** (not on the exam but you should know what it is)
	Recon – Weapon – Delivery – Exploitation – Installation – C2C - Actions

----------
<u>Module 2 Threat Mgmt and Cybersecurity Resources</u>
Pen Test – attempts to exploit vulnerabilities just like a threat actor would
Red Team – attackers or pen testers
Blue Team – defenders or system and network admins / IT security personnel
White Team – referees, enforce rules of engagement
Purple Team – bridge communications and knowledge between red and blue team
Types of Pen Tests:
Black box: testers have no knowledge of the network and no privs
Gray box: testers are given limited knowledge of the network and some privs
White box: testers are given full knowledge of network and source code of apps
**Pen Test terms:**
- Rules of engagement: what you are allowed to do as a tester
- Scope: what should be tested and what are the boundaries
Vulnerability Scan: using an automated tool (ie., Nessus, Armitage) to scan for known
vulnerabilities.
- Credentialed: scanner is given credentials to login to systems
- Non-credentialed: scanner can only see what is available from the network
SIEM (Security Information and Event Management) (Splunk, Zeek, MCAS)
(usually pronounced “seem”) a product that consolidates real-time security monitoring
and management of security information.
- Aggregation: collecting and indexing logs
- Correlation: looking for common characteristics
- Alerting: generating alerts when certain events trigger additional investigation or
action

---------
<u>Module 3 - Threats and Attacks on Endpoints</u>
**Terms:**
Endpoints: workstations, mobile phones, laptops, servers, appliances, ioT
Malware: malicious software, file based, LOLBins (living off the land uses
existingservices and binaries)
Ransomware: (imprison), encrypts files until fee is paid (bitcoin facilitates)(latest
ransomware encrypts and threatens to publish all data publicly)
(Story about University of Hawaii and attack from nation state, submarine research,
memory based malware that could only be detected if memory dump was done)
Worm: uses network to replicate (sasser)
Bot: hacked PC / computer under remote control
Botnet: collection of bots
C&C : (Command and Control) traffic to/from a botnet is called C2 or C&C traffic
(Modern firewalls Next Gen or 4th Gen or layer 7 firewalls / IDS/IPS detect C2)
IDS: Intrusion Detection System IPS: Intrusion Prevention System
Spyware: spies on victims and collects personal or sensitive info ie passwords
(keylogger for example, why password manager is a good idea)
(keylogger can be software or hardware) (do you check every day the
back of your PC?, nope)
PUPS: Potentially Unwanted Program
Trojan: masquerades a something benign but does malicious activity in background
(early mobile phone ringtones were notorious for being trojans)
RAT: Remote Access Trojan or Remote Access Tool (aka root kit)
Backdoor: embedded software / trojan that gives unauth remote access
Logic Bomb: program that does malicious things when a date or event is met
Rootkit: low level malware that hides other malware
Attacks:
XSS: cross site scripting (website accepts user input without checking or sanitizing
it, ie., webform or discussion forum. Posted comment may redirect you to another
page)
SQL injection: insert code into input fields to manipulate or trick database)
XML injection: using XML (eXtensible Markup) instead of SQL (Standard Query
Language)
CSRF: cross-site request forgery, uses an auth token from 1 website to do activity
the user is unaware of, usually by loading another webpage
SSRF: server-side request forgery, similar to CSRF but between backend servers
Buffer Overflow: program tries to store data beyond fixed-length storage, may
allow attacker to point program to another memory location and execute malicious code
Integer Overflow: variable is set to something not expected or accounted for and
potentially crashes the program or forces it to exit, sometimes getting you a command
prompt
AI: artificial intelligence (security portals spotting anomalies, threat indicators)
ML: machine learning (using datasets to train an algorithm then it trains itself)
USB Drop: dropping malicious USB memory sticks in the parking lot of a targeted
company or organization. (See “Hak5.com Rubber Ducky, USB keystrokes…

----
<u>Module 4: Endpoint and Application Development Security</u>
Threat Intelligence Sources:
White Hat Hackers, bug bounty programs, corporations paying researchers/hackers for
notifying them of discovered bugs.
Google Project Zero: established fixed schedule/deadline for publicly disclosing
vulnerable software to encourage developers to fix their code in a timely fashion.
Open Source Intel: (OSINT) publicly available freely shared threat info. (Cisco Talos,
other “block lists” and IP / Domain reputation websites)
Closed Source Intel: shared among and organization where members are vetted, ie.,
REN-ISAC, MS-ISAC or pay to play subscriptions like Cisco / Webroot.
CVE: Common Vulnerabilities & Exposures ie., CVE-2021-1886
CVSS: Common Vulnerability Scoring System 1-10, 10 is bad! Very bad!
AIS: Automated Indicator Sharing (TAXII & STIX, 2 formats/protocols)
KRI: Key Risk Indicator
IOC: Indicators of Compromise, usually a list of IP addresses or domain names / URLs
Vulnerability Databases: lists / examples of known vulns (Nessus, Metasploit)
Dark Web: part of the Internet that is beyond the reach of common search engines and
is the domain of threat actors, criminals and some info sec researchers
Anti-virus (AV): endpoint program responsible for identifying and blocking malicious
programs and activity
EDR: Endpoint Detection and Response, (new name for better anti-virus)
- An example is Microsoft Defender for Endpoint Advanced Threat Protection (ATP).
MDATP has advanced reporting and blocking capabilities allowing the enterprise to
manage endpoints from a central console and track / isolate malware while still
communicating with the endpoint/workstation (HIDS, HIPS, EDR…)
Signature based / Static AV: AV that looks for specific strings or code in a file
Heuristic based / Dynamic AV: AV that looks at process & program behavior
Bayesian filtering: technique used to detect and filter spam email
BIOS: basic input output system
UEFI: Unified Extensible Firmware Interface (BIOS with new features, networking…)
Secure Software Development and Operations (DevOps):
Static code analysis: assessing code (source code) before compiling (use free tools)
Dynamic code analysis: testing after compilation (tools are available)
Fuzzing: technique of generating random input to a program to see what happens
Sandbox: “container” for application to run in so it can’t reach the underlying OS

--------
<u>Module 5: Mobile, Embedded & Specialized Device Security</u>
Mobile Devices: tablets, smart phones, wearables (Fitbit), laptops, Chrome-book (web-
based)
- Network connectivity: Wi-Fi, Bluetooth, Cellular, USB (mini, micro) Infra-red (rare)
- Small form factor, Mobile OS
- GPS / location services
Corporate provisioning:
BYOD: bring your own device
COPE: corporate owned personally enabled
CYOD: choose your own device
VDI: virtual desktop infrastructure
CO: corporate owned
Mobile Device Vulnerabilities & Risks:
- Physical security: they can be lost or stolen (was device encrypted? Disk
encrypted?)
- Limited OS updates: should be automated but some users resist
- Location tracking: GPS allows tracking, GSP allows tagging
- Unauthorized recording: spying, audio & video (Edward Snowden, Citizen 4
documentary)
- Connectivity risks: tethering, OTG (on-the-go), malicious usb (charging / data),
insecure hotspots
Mobile config best practices:
- Strong authentication, PIN, fingerprint, facial recognition, enable encryption
- Automatic updates enabled
- Do not allow jailbreaking, rooting or sideloading
-------
<u>Module 6: Basic Cryptography</u>
Terms:
- Hash: A digital fingerprint, a one-way algorithm that produces the fingerprint
sometimes call a “digest” or “message digest” (MD, ie., MD5)
- Blockchain: A shared immutable ledger that records transactions and tracks
assets
- Downgrade attack: Requesting the system abandon higher security mode of
operation and “fall back” to older less secure protocols
- Steganography: Hiding data within another file type, such as an image file
- ==🟣ROT13: “rotate by 13 places”, a simple letter substitution cipher that replaces a
letter with the 13th letter after it.
- ==🟣DES: Data Encryption Standard, early 1970’s first widely used symmetric (1-key)
algorithm
- ==🟣3DES: Triple DES, uses 3 rounds of encryption using different keys for each round,
performs better in hardware
- ==🟣AES: Advanced Encryption Standard, symmetric cipher, approved late 2000 to
replace DES. Fed govt standard, AES-256 uses 256-bit key. To date, no known
attacks on this cipher.
- ==🟣RSA: The most common asymmetric (2-keys) algorithm
- ==🟣Encryption: The process of changing original text into a secret message using
cryptography
- ==🟣Key: a mathematical value entered into an algorithm to produce ciphertext
- ==🟣Decryption: The process of changing ciphertext back to original text, usually
requiring the use of a key.
- ==🟣TLS1.2: The current minimum standard encryption protocol for PCI-DSS for
information in transit / transmission.