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
		1. Use Event Viewer to search for errors and warnings
			- Recall that the Administrative Events log in Event Viewer collects errors and warnings to help with problem-solving. Investigate warning and error events that might point to the source of the problem. A web search on the message can help.
		2. Update Windows and verify anti-malware settings
			- Make sure Windows is updated, and other Microsoft products are included in Windows updates. Eliminate malware by checking that anti-malware settings are correct. If you find real-time protection is not on, do a full scan for malware
		3. Suspect a corrupted application or supporting service
			- If you observe that instability happens when a particular application is running, try to repair the application. If that doesn’t work, uninstall and reinstall the app
		4. Suspect faulty memory
			- Errors with memory are often difficult to diagnose because they can appear intermittently and might be mistaken for application errors, user errors, or other hardware component errors. With memory errors, the system may hang, a BSOD (blue/black screen of death) error might occur, or the system may continue to function, with applications giving errors or data being corrupted. You can quickly identify a problem with memory or eliminate memory as the source of a problem by using the Windows Memory Diagnostics (mdsched.exe) tool
		5. Suspect a corrupted hard drive
			- To eliminate the hard drive as the source of an unstable system, run the ==🔵chkdsk c: /r== command to check the drive. The error-checking utility searches for bad sectors on a volume and recovers the data from them if possible. It then marks the sector as bad so it will not be reused. Also check Event Viewer for warnings or errors regarding the hard drive.
		6. Suspect corrupted Windows system files
			- Use the System File Checker (SFC) to scan for corrupted or missing system files, and replace them with a fresh copy. Enter the sfc /scannow command in an elevated command prompt window. If you still have problems, use System Configuration to perform a Safe boot. In Safe Mode, enter the sfc /scannow command. If that doesn’t solve the problem, try System Restore
		7. Suspect corrupted device drivers
			- Check Device Manager for errors. If a device shows a problem that has recently been updated, roll back driver updates. Try updating drivers. Try uninstalling and reinstalling the device
		8. Suspect corrupted third-party services or apps running in the background
			- perform clean boot: disable all third party services in msconfig.exe, disable startup apps in Task Manager and restart Windows
			- re-enable services one by one until you zero in on the problem app
		9. Suspect the Windows installation is corrupted
			- By now in the troubleshooting process, you have eliminated memory, the hard drive, Windows system files, malware, and third-party services and programs as the likely source of system instability. It’s time to consider the entire Windows installation might be corrupted. Recall from the chapter “Installing Windows” that you can repair Windows 10/11 by performing an in-place upgrade. Follow directions given in that chapter to download and upgrade the Windows 10/11 installation. If the problem is still not solved, consider whether the CPU or motherboard is failing
- **Application Errors and Crashes**
	- backup data and do the following
		1. *End a hung application* - use Task Manager, or ==🔵taskkill /f /pid:xxxx==, with PID from the process in Task Manager
		2. *Search the web on error messages and symptoms* 
		3. *Consider data corruption* - try creating a new data file and see if the problem persists
		4. *Check application settings and logs for errors* - write down each setting the user has changed, then restore all settings back to their default values. If the problem is solved, restore each setting back one by one until the find the problem setting
		5. *Repair or update the application*
		6. *Uninstall and reinstall the application* - do so with caution as you may lost customized settings, macros, or scripts. Still may not solve the problem with a corrupted application because registry entries might not be properly reset during the uninstall process
