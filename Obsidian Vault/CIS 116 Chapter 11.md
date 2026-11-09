<u>Objectives</u>
1. Understand the composition of a VM
2. Examine using templates
3. Understand how to clone a VM
4. Examine VM snapshots

-------------
- **Cloning VMs**
	- copying VM files (.vbox, .vdi, .vmx) duplicates the VM, including the virtual hardware and software
	- some work must be done to ensure that the new VM has a unique identity or network errors will result
	- Sysprep is a Windows utility that can be used to automate the customization of a cloned VM
		- sysprep can alter device drivers and add applications in addition to providing identification information
	- full clones are replicas of the original VM and require the same storage space
	- linked clones use the original VM for reference, and any changes are kept in a delta disk
		- this requires much less space than a full clone, though it could cause performance issues
- **VM Templates**
	- templates are models of VMs that can be cloned
	- usually stored as VMs that cannot be powered on (read-only state) to help prevent unintended changes
	- configured to be "golden images" (validated and approved combination of operating system with patches, corporate approved utilities, and sometimes application installations)
	- templates are also created through the use of management tools
- **Working with Snapshots**
	- snapshots capture the entire VM state in a moment in time
	- not to be used as a backup solution due to potential performance issues
	- lock the original VM disk and create child a disk where changed blocks are written
	- when the user reverts to the snapshot, the child disk is erased, and the changes start again
	- multiple snapshots can be taken, creating sophisticated branches of a development or test cycle
	- deleting snapshots removes the child disk with the changes allowing the original disk to be written to once again
	- merging the changes into the VM collapses the changed blocks back into the original disk, which can be written to again
- **Linked Clones**
	- conserves disk space
	- changes to parent don't affect clone, changes to clone don't affect parent
	- clone MUST have access to parent
	- possible to make linked clone of a linked clone, but lose performance
	- making a full clone of a linked clone creates an independent VM
	- cannot delete the underlying snapshot of the parent without deleting the linked clone that relies upon it
