*Objectives*
	- Understand the steps to load Ubuntu Linux into a VM
	- Understand the steps needed to install the VirtualBox guest additions into a Linux VM
	- Examine some VM configuration options
	- Examine some optimizations for a Linux VM

- **Proper Linux Timing**
	- All VMs require proper time synchronization; however, Linux had been particularly susceptible to timing issues
	- VMs have no distinct CPU clock so they depend on their host's clock
	- Network Time Protocol (NTP) allows multiple hosts to stay in time sync
	- Less of an issue with modern improvements to kernel routines
- **Optimizing a Linux VM**
	- certain daemons that run on Linux are not necessary in a virtual environment, disable to conserver resources
	- blah blah blah delete daemons and only install packages you need, keep it trim, worthless notes