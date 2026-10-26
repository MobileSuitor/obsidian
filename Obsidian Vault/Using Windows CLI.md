- Two levels of command prompt windows: standard and elevated
	- *Standard* - default directory is currently signed-in user's folder and commands have the same permission as that user
	- *Elevated* - commands have administrative privileges, default directory is C:\Windows\System32
- Commands are **_not_** case sensitive in Windows
- https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands

| Command            | Description                                                                             |
| ------------------ | --------------------------------------------------------------------------------------- |
| help               | Lists all commands, or the specific<br>command provided as an argument                  |
| winver             | Displays the About Windows box                                                          |
| dir                | Lists files and directories                                                             |
| dir /p             | Lists one screen at a time                                                              |
| dir \<filename>    | Checks that a file is present                                                           |
| dir /w             | Presents in wide format, details are<br>omitted and files/folders are listed in columns |
| dir \*.txt         | Lists all files with .txt extension in default path                                     |
| dir d:/data/\*.txt | Lists all files with a .txt extension in the <br>specified file path                    |
| dir /s             | Includes subdirectory entries                                                           |
| dir /a             | Lists all files, including hidden files                                                 |
| cd                 | Change directory                                                                        |
| md (mkdir)         | Creates a directory                                                                     |
| del                | Deletes files                                                                           |
| attrib             | Changes system and hidden attributes for a file                                         |
| rmdir              | Deletes a directory (only if empty)                                                     |
| rmdir /s           | Deletes a directory that is not empty                                                   |
| robocopy           | Copies a single file and directories, logs activity,<br>moves files, or purges files    |
| chkdsk             | Fixes file system errors and recovers data from<br>bad sectors                          |
| format             | Formats a hard drive or other storage device                                            |
| diskpart           | Manage partitions                                                                       |
| sfc /scannow       | System File Checker, repairs corrupted files                                            |

- **Robocopy example commands**
	- ==robocopy C:\docs\*.* E: /s== - copies all files in the first file path to drive E. The /s option includes subdirectories in the copy, but not empty ones
	- ==robocopy C:\docs\*.* E: /e== - same thing as above. The /e option includes empty subdirectories
	- ==robocopy C:\docs\*.* E: /log:Mylog.txt== - records activity to a log file and overwrites the current log file
	- ==robocopy C:\docs\*.* E: /log+:Mylog.txt== - same as above, but appends to existing log file instead of overwriting
	- ==robocopy C:\docs\*.* E: /move== - moves files and directories, **_deleting_** them from the source
	- ==robocopy C:\docs\*.* E: /purge== - deletes files and directories at the destination that no longer exist at the source
- **Format example commands**
	- ==format D:== - performs a full format of volume D: using the default file system for the volume type 
	- ==format D: /q== - performs a quick format by recreating an empty root directory. Use when formatting a previously formatted disk that is in good condition
	- ==format D: /fs:NTFS== - specifies file system to use (NTFS)
	- 