- [[Table 14-2 Common Windows problems and Solutions After Startup]]
- **Steps to Solve Any Computer Problem**
	1. *Identify the problem* - begin by interviewing the user. Find out if the user has recently changed anything, and ask what happened around the time the problem started, such as recent thunderstorms and changes on the network. Also ask if valuable data is on the system, and back it up if necessary.
	2. *Establish theory of probable cause* - ask the user to reproduce the problem while you watch. Many problems with applications are caused by user error. Watch carefully as the user shows you the problem. If you notice them making a mistake, be tactful as you explain the problem and solution
		- **Try rebooting the system** - solves a lot of application problems, pay attention to any error messages during startup
		- **Use Event Viewer, Task Manager, and Resource Monitor** - useful for finding error messages and events, services that failed to start, and apps and devices hogging resources
		- **When in doubt, web search and ask coworkers**
	3. *Test theory and fix the problem*
	4. *Verify, prevent, and document* - do one final reboot, then verify with user that all is working to their satisfaction. Implement preventative measures as appropriate, and don't forget to document findings
- **Services Not Starting**
	1. *Task Manager* - open Task Manager to find out what's currently running. On the Processes tab, you can verify the app is running but not the background process it requires. Checking the Services tab allows you to discover that the status of the service is stopped, start it up again
	2. *Services Console* - next you need to determine why the service was not running in the first place. Open the Services Console to make sure that the service is configured to start each time Windows starts 
	3. *Final reboot* - reboot the system to verify that the service and app are working as they should. If problems persist, you might need to uninstall and reinstall the service or the application. Sometimes using the Programs and Features window to repair the application will take care of the problem
- **USB Controller Resource Warnings** 
	1. *Device Manager* - Check Device Manager for errors. Sometimes disabling or uninstalling a device and then enabling or reinstalling it can fix a problem. You can also try updating the USB drivers from Device Manager; however, a better option is to go to the motherboard manufacturer website and download and install the latest chipset drivers on the motherboard
	2. *Power Options* - open Power Options in Control Panel and disable USB selective suspend. Sometimes lowering the power state of inactive USB ports can make them unreliable
- **Time Drift**
	- happens when a Windows system does not report accurate time to time-sensitive applications
	- on a Windows domain, clients can request the time via the Windows Time Service (W32Time)
		1. Services console > set W32Time service to automatic startup
		2. Edit registry to set values such as time intervals to poll the time server and the number of clock ticks to adjust for network latency
		3. Stop and start the time service so the registry changes take effect
		4. to display the Stratum level assigned to a workstation, enter ==🔵w32tm /query /status==
- **Low Memory Warning**
	- may be issued due to lack of memory for applications running, malware sucking up resources, lack of space on hard drive to hold virtual memory, or too many apps and background processes running
		1. *Task Manager* - open and check Processes tab to find out which programs are using the most memory. Use Resource Monitor for more details on how memory is being used
		2. *Research the web* - if you find a suspicious process, look it up and try to determine if it is malware or is notorious for high memory usage. Uninstall if not needed
		3. *Low on resources* - Windows uses both physical memory and virtual memory stored in pagefile.sys on the hard drive. The problem might be not enough of either
		4. *System Information* - use System Information to find out how much physical memory is installed
		5. *Update chipset drivers* - updating motherboard chipset drivers might help on new installations of Windows
- **Degraded Performance**
	- can be caused by variety of issues: malware, low system resources, too many programs running, corrupted Windows installation. Do the following after backing up data
		1. *Observe the system* - use Task Manager and Resource Monitor to help identify programs that can be disabled or uninstalled
		2. *Verify Windows updates and antivirus settings* - install the latest updates, and verify the system is scanning for malware
		3. *Uninstall applications you no longer need, and optimize the hard drive* - frees up space on the hard drive, verify there is at least 15-20% free space for Windows overhead and that the drive is optimized
		4. *Verify requirements for the OS and applications* - use System Information to find the model and speed of installed processor and hard drive as well as the amount of memory installed. Compare with minimum requirements for the Windows installation. Performance Monitor can provide more info if you suspect the CPU, hard drive, or memory is the bottleneck. Video bottlenecks may be solved by updating drivers
		5. *Search for unnecessary startup programs you can eliminate* - through Task Manager
		6. *Disable or uninstall startup items* - temporarily disable to test if performance improves
		7. *Search for unwanted scheduled tasks* - open Task Scheduler and determine if any tasks are unnecessary or causing issues.
	- extremely slow systems may need a clean boot
- **System Instability**
	- Unstable systems may hang, throw errors at any time or even shut down unexpectedly. Can be caused by a virus, corrupted data files, Windows system files, application software or device drivers, or by failing essential hardware devices