<u>Objectives</u>
1. Explain the steps in preparing for a cybersecurity incident
2. Describe how to respond in an incident
3. List the steps in an incident investigation

----------------

- **Action Control Schemes**
	- *Discretionary Access Control (DAC)* - least restrictive, giving an owner total control over objects and who else can access the owner's objects. 
		- Weaknesses: relies on decisions made by the user to set proper level of security, permissions will be inherited by any programs executed by the owner 
	- *Mandatory Access Control (MAC)* - most restrictive, assigns user's access controls strictly according to the custodian's desires
	- *Role-Based Access Control (RBAC)* - based on a user's job function within an organization. Permissions are assigned to particular roles in an organization and then users are assigned to these roles
	- *Rule-Based Access Control* - dynamically assigns roles to subjects based on a set of rules defined by a custodian. Used for managing user access to one or more systems
	- *Attribute-Based Access Control (ABAC)* - uses flexible policies that can combine attributes
- **Preparing for an Incident**
	- *Creating an Incident Response Plan* - set of written instructions for reacting to a security incident, incident response process consists of six steps:
		1. Preparation - equipping IT staff, management, and users to handle potential incidents
		2. Identification - determining whether an event is actually a security incident
		3. Containment - limiting the damage of the incident and isolating those systems that are impacted to prevent further damage
		4. Eradication - finding the cause of the incident and temporarily removing any systems that may be causing damage
		5. Recovery - permitting affected systems to return to normal operation
		6. Lessons Learned - completing incident documentation, performing detailed analysis to increase security and improve future response efforts
- **Studying Attack Frameworks**
	- three common attack frameworks:
		1. *MITRE ATT&CK* - knowledge base of attacker techniques that have been broken down and classified in detail
		2. *Diamond Model of Intrusion Analysis* - framework for examining network intrusion events
			![[Pasted image 20261123112814.png]]
		3. *Cyber Kill Chain* - exploitation framework that outlines the steps of an attack in an integrated and end-to-end process. Reconnaissance > Weaponization > Delivery > Exploitation > Installation > Command & Control > Actions on Objectives
- **Incident Response**
	- *Use SOAR Runbooks and Playbooks* - Security, Orchestration, Automation, and Response products can help security teams manage and respond to security warnings and alarms
		- Playbook - linear-style checklist of required steps and actions needed to successfully respond to specific incident types and threats
		- Runbook - series of automated conditional steps that are part of an incident response procedure
	- *Perform Containment*
	- *Make Configuration Changes*
- **Incident Investigation** 
	- *Data Sources*
		- Log files - firewall logs, NIDS/NIPS logs, web servers, DHCP servers, etc.
		- 