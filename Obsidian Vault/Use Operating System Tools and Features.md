<u>Objectives</u>
- explore Windows Administrative Tools and Computer Management interfaces
- Task Scheduler for creating tasks
- check systems for memory issues
- review effective permissions
- implement Windows File History
- configure app control policies using Local Group Policy

<u>Windows Administrative Tools and Computer Management Interfaces</u>
- right click start button > Computer Management
- three categories: System Tools, Storage, Services and Applications
- Windows Tools can be accessed from the search bar
- both interfaces share some tools, but some are only available in one or the other

--------------------
<u>Task Scheduler</u>
- can be used to schedule custom tasks, such as opening Command Prompt automatically when logging on
- useful for automating simple or mundane tasks, kinda like scripting but more restrictive since its Windows slop

--------------
<u>Review effective permissions</u>
- check permissions for files through Properties > Security tab
- effective access for a specific user can be seen in the Advanced settings > effective access tab > select user > Advanced > Find Now > select user and hit OK > view effective access
- Effective Access tool is only a predictive utility; it does not actually change group memberships or access permissions, but can be used to test a hypothesis or troubleshoot access issues
- granting group access to a file
	- Security tab > Advanced settings > Add > Select a principal > enter group name in bottom field
	- select permissions from list

--------------------
<u>Implement File History</u>
- File History > Turn on for desired drive
- restore personal files on left panel
- Necessary to hit run now to save any configuration changes

------------
<u>Configure application control policies with Local Group Policy</u>
- Application Identification service - run with ==net start appidsvc== - requires elevated terminal
- Configure AppLocker rule enforcement - enables and enforces rules for Executables, Windows Installer, Scripts, and Packaged apps
	- Windows search bar: policy > edit group policy
	- left pane: Computer Configuration > Windows Settings > Security Settings > Application Control Policies > AppLocker
	- Configure Rule Enforcement > configure all
	- Can also create specific rules, i.e. Executable rule to deny access to regedit.exe
	- Difference between *Path* and *File Hash* rules:
		- *Path* rule simply denies application from running based on name and location of file, so if a file is moved or renamed it can still execute
		- *Hash* rule generates a hash of the file, so if the file is moved or renamed it will still not execute. Use more overhead but are more restrictive
- Force Group Policy update
	- use ==gpupdate /force==
	- gpupdate documentation --> https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/gpupdate