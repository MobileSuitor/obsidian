Microsoft Learn diskpart documentation ---> https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart

- Two ways to manage Disk Partitions: Disk Management GUI and ==diskpart== in Terminal
	- Disk Management
		- delete and create partitions on a given disk by right clicking and selecting the appropriate menu option
		- New Simple Volume Wizard walks you through the steps
		- keep Perform a quick format option checked
	- ==diskpart==
		- open terminal and run ==diskpart== to start utility
		- ==list disk== displays a list of all local disks
		- use ==select disk x==, with x being the number of the disk you want to work with
			- can also be used on ==partition==
		- use ==list partition== and ==create partition primary== 
		- run ==format fs=ntfs label="Drive_Name" quick== to format the selected partition with NTFS and assign a label
		- ==detail disk== for more info
		- ==assign letter=g== assigns G to current selected volume indicated by asterisk
- ==chkdsk== command - needs elevated terminal session, use ==chkdsk== followed by drive letter (g:), add >report.txt to save to text file named report