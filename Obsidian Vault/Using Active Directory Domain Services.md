- Active Directory is a a suite of services and databases provided by Windows Server that is used to manage Windows domains. AD incorporates five groups of services:
	1. *Active Directory Domain Services (AD DS)* - authenticates accounts and authorizes what these accounts can do
	2. *AD Certificate Services (AD CS)* - secures identities of services, computers, and users
	3. *AD Federation Services (AD FS)* - secures trust relationships with outside organizations
	4. *AD Rights Management Services (AD RMS)* - secures data
	5. *AD Lightweight Directory Services (AD LDS)* - secures applications
- **AD Resource Organization** - uses top-down hierarchical structure, where users and resources of a company or school managed by AD are organized into a forest (the entire enterprise), which contains a domain. 
	![[Pasted image 20261105141158.png]]
- **Organizational Units (OU)** - objects that define a collection of user groups and/or computers in AD. These are created to make it easier for technicians to assign privileges to users and computers that are assigned to an OU
	- can contain groups of users or computers called **security groups**, which are similar to user groups in a Windows workgroup except a security group can include a computer or a user
- **Group Policy Objects (GPOs)** - a named set of policies that have been created by Group Policy and are applied to an OU
	- good hands on practice for managing GPOs is on pg. 884
- **Creating and Managing User Accounts in AD**
	- this section is all hands on stuff, refer to pg. 875 for exercises
- 