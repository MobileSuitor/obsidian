<u>Objectives</u>
- prepare for backup operations
- configure Windows File History and perform a backup
- restoring deleted files from backup
- enable Volume and Shadow Copy Service
- using system restore points

<u>Copying files</u>
- syntax is ==copy== {file} {C:\path\to\directory\filename}
- make sure you're in the correct directory first using ==cd==
---------------
<u>Configure Windows File History and perform backup</u>
- enable File History for a given backup drive through Backup Settings > Add a drive > select drive
- folders that are marked for backup can be edited under More options once backup drive is selected
- time interval of backups and duration backup files are kept can also be edited here

----------------------------
<u>Restoring deleted files from backup</u>
- select Restore your files with File History from search bar
- select folder containing document you want restored, select document
- you can restore to original location, or select an alternative one using the gear icon
-------------
<u>Enable Volume Shadow Copy Service</u>
- first enable a Restore Point for the desired drive, turn on system protection option and select maximum disk usage for restore points 
- hit Create and designate a name
- now you can force Volume Shadow Copy Service (VSS) to make a backup of a drive
	- open cmd as Admin and run ==wmic shadowcopy call create Volume=c:\==
	- normally, VSS will retain a copy of a file just as a change is performed, but this can be unreliable so it is recommended to force the operation
	- VSS will retain previous versions of files, but it is **NOT** a backup. If a file is removed from a dive VSS cannot be used to restore it. Use File History or system restore points for this instead

----------------
<u>Using restore points</u>
- right click a drive and go to Previous versions tab, select timestamp option and hit Open to see file path and confirm files to be restored
	- notice the path is mapped through Network, this allows for file operations between the restore point files and the regular storage system
- instead of restoring an entire drive, you can copy individual files and paste them into another drive 
- System restore points and VSS File History is located on the storage device, so if it is damaged then these backups are lost