- VMs and their settings are described in a settings file in XML format
- virtual disks, represented by disk images, are usually in VDI format
- **VM Folder** - stores XML settings file w/ .vbox extension and disk images
	- created in current user's home directory by default
		- On Windows - location is what is returned by SHGetFolderPath function of Windows system library Shell32.dll. Typical location is C:\Users\\*user*
		- On Linux and macOS - generally taken from environment variable $HOME, except for the root user where it is taken from the account database. Typically /Users/*user*
- **Global Settings** - locations where global configuration data is maintained
	- Linux - $HOME/.config/VirtualBox
	- Windows - $HOME/.Virtualbox
	- macOS - $HOME/Library/VirtualBox
- **Logs** - useful for troubleshooting errors, stored in the *Logs* folder under the VM folder
- **Snapshots** - saves a particular state of a VM to return to, useful for testing stuff and then reverting if anything breaks. Contains a complete copy of VM settings, the state of all virtual disks attached to the machine

<u>File Types</u>
- .vbox - machine settings file (XML) in the VM folder
- .vdi - VirtualBox Disk Image, the VM's virtual hard disk
- Logs folder - VBox.log, written each time the VM starts
- Snapshots folder - differencing disk images and saved states
- VirtualBox.xml - global settings file, including the list of registered VMs