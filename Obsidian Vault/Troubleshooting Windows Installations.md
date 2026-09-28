- **Dealing with Old and Unknown Product Keys** - suppose a hard drive that has a Windows installation fails and you must install Windows on the replacement drive, or you want to move the Windows installation from one computer to another. 
	- There are three ways to acquire Windows:
		1. *Original Equipment Manufacturer (OEM) license* - cheaper than retail license and purchased from third-party vendors. Associated with the motherboard on which it is first installed, <u>can't be transferred to a new motherboard</u> but can work with a new hard drive
		2. *Retail license* - purchased from Microsoft online store or from retailers. Product key is sent to email address used to make the purchase. <u>License follows Microsoft account email from one PC to another</u>
			- if you don't know the email address that was used for a retail license, you can find the product key by opening command prompt as Admin and entering: ==wmic path softwarelicensingservice get oa3xoriginalproduct key== 
		3. *Digital license* - Microsoft still unofficially offers a free upgrade to Windows 10/11 from 8.1 or 7. Does not have a product key associated with it, but gets assigned a digital license
	- When installing Windows 10/11 on a new hard drive:
		- Microsoft retains info about the system Windows is installed. When performing a clean install on a new hard drive in this system, Microsoft recognizes the system. Click **I don't have a product key** during setup and it should activate
		- Moving retail license to new computer - enter product key purchased from Microsoft store. Check order history if key is unknown
		- OEM licenses cannot be moved, you must purchase a new OEM license for a new computer 