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
	- 