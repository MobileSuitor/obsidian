<u>Module objectives</u>
1. explain what a penetration test is
2. identify the rules of engagement and how to perform a pen test
3. define vulnerability scanning
4. describe different cybersecurity resources

- **Penetration testing** - attempts to exploit vulnerabilities just as a threat actor would, with the goal of uncovering new vulnerabilities, providing a clearer picture of their nature, and determining how they could be used against the org
	- *Planning is critical* - lack of planning can result in a flawed test that tries to do too much or too little. Can also result in *creep*, or an expansion beyond the initial set of the test's limitations
	- can detect a different kind of vulnerabilities than a network scan. Scans usually only detect surface problems due to being entirely automated and providing limited verification. Pen tests can find much deeper vulnerabilities using manual techniques
	- *Who performs the test?* 
		- **Internal Security Personnel** - <u>advantages</u> include little to no additional cost, tests can be performed very quickly, and can also be used to enhance training of employees and raise security awareness. Also several <u>disadvantages</u>: inside knowledge prevents true simulation of attacker, lack of expertise may limit the ability to perform a comprehensive test, or they may be reluctant to reveal a vulnerability that they or a fellow employee were charged with protecting
		- **External Pen Tester Consultant** - <u>Advantages</u>: higher technical and business expertise, higher credentials and certifications, more pen testing experience to look for vulnerabilities, and a deeper focus on the task of testing. <u>Disadvantages</u>: consultants may receive sensitive info about network that could be sold to competitor, NDAs are signed to prevent this
			- *Black Box* - testers have no knowledge of network, emulates exactly what an attacker would do and see, though if they can't successfully penetrate then no test can occur
			- *Gray Box* - testers are given limited knowledge of the network and some elevated privileges. This lets them more efficiently assess security, but does not completely simulate the position an attacker would be starting from
			- *White Box* - testers are given full knowledge of network and source code of applications. This allows them to focus directly on systems to test for penetration, but does not provide a full picture of the network's vulnerabilities
		- **Crowdsourced Pen Testers** - involves a large group of individuals who are not regular employees of the contractor. <u>Advantages</u>: faster testing, ability to easily rotate teams so different people test the system, and can conduct multiple pen tests simultaneously
- **Rules of Engagement** - limitations or parameters of a pen test, keep a test focused and effective. Categories of RoE listed below:
	- *Timing* - when the test will occur and how long it will take. Timetable of test can be greatly affected by the discovery of a large bug, subsequent meetings with personnel to address the vulnerability, etc. 
	- *Scope* - what should be tested. Involves several elements that define relevant test boundaries:
		- **Environment** - live test environment, or simulated sandbox? Live provides the most accurate test, but can disrupt operations.
		- **Internal Targets** - must be defined for external gray box or white box test. Can include IP addresses, network ranges, domain names. Must account for systems like firewalls, intrusion detection and prevention systems, and networking equipment between tester and final target. **VALIDATE** that these targets belong to customer before testing
		- **External Targets** - test may include testing a service or an application hosted by a third-party
		- **Target Locations** - laws vary among states, provinces, and countries, so tests must take into consideration the physical location of the target and adjust accordingly
		- **Other Boundaries** - things other than technical boundaries, such as if the test should include physical security like fences, cameras, and guards. Social engineering targets, phishing message targets
	- *Authorization* - receipt of prior written approval to conduct the pen test
	- *Exploitation Level* - should a vulnerability always be exploited when uncovered? Are specific areas "off limits" so that the tester should not view related data?
	- *Communication* - particularly important between tester and org. Includes the following:
		- **Initiation** - org should be notified when test begins
		- **Incident Response** - if a tester can complete the initial assessment without triggering the org's incident response mechanism, then a critical gap in the security structure has been identified
		- **Status** - best to provide periodic status reports throughout the test
		- **Emergency** - critical vulnerabilities should be immediately reported while the test is paused
	- *Cleanup* - must ensure everything related to the test is removed after its completion. Removing software agents, scripts, executable binaries, temporary files, and backdoors.
	- *Reporting* - generated to document the objectives, methods used, and results of a completed test. Divided into two parts, with the first part being an executive summary for less technical audience, and the second part being more technical in nature for security professionals
- **Test Phases** - can be split into two, reconnaissance and penetration
	- *Reconnaissance* - preliminary information gathering from outside the org. <u>Active Reconnaissance</u> involves directly probing for vulnerabilities and useful info, but probes are likely to alert security professionals within the org that aren't aware of the pen test. <u>Passive Reconnaissance</u> uses tools that do not raise any alarms, such as searching online for publicly accessible information
	- *Penetration* - executing the actions a threat actor would when discovering a vulnerability. Gaining access to the system, escalating privileges, moving through the network looking for more vulnerabilities, and installing a backdoor for repeated access
------------------------------
- **Vulnerability Scanning** - frequent and ongoing process, often automated, that continuously identifies vulnerabilities and monitors cybersecurity progress. Purpose is to reduce the attack surface 
- **Types of Scans** 
	- *Credentialed vs Non-credentialed Scans* - whether or not valid authentication credentials are supplied to the scanner. Non-credentialed scans are faster because they perform fundamental actions such as looking for ports, but credentialed scans can provide a deeper insight into the system 
	- *Intrusive vs Nonintrusive Scans* - intrusive scans attempts to employ any vulnerabilities that it finds, while nonintrusive scans only record what they discover. Intrusive scans are more accurate, but may impair the system. Nonintrusive can only indicate that something *may* be vulnerable 
-----------------------
- **Cybersecurity Resources** 
	- *Frameworks* - series of documented processes used to define policies and procedures for implementing and managing security controls in an enterprise environment (NIST, ISO, AICPA, CIS, CSA)
	- *Regulations* - standards typically developed by established professional organizations or government agencies
	- *Legislation* - vary state to state, can often contradict each other 
	- *Standards* - a document approved through consensus by a recognized standardization body. It provides for frameworks, rules, guidelines, or characteristics for products or related processes and production methods. Compliance not mandatory, but there are restrictions for those that do not comply
	- *Benchmarks/Secure Configuration Guides* - guidelines for configuring a device or software usually distributed by hardware manufacturers and software developers.
	- *Information Sources* - can include vendor websites, conferences, academic journals, local industry groups, and social media.