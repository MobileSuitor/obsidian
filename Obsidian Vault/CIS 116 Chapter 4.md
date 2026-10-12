*Objectives*
	- Understand P2V (Physical-to-Virtual) conversions
	- Load VMware Player as a virtualization environment
	- Load Oracle VirtualBox as a virtualization environment
	- Create a new virtual machine

- **The P2V Process**
	- P2V creates virtual machines using existing physical servers as their templates
	- *Consolidation*: removing physical servers from a datacenter by virtualizing them onto fewer hosts
	- *Containment*: Deploying new applications directly into a virtual environment
- **Hot and Cold Cloning**
	- Hot cloning creates a virtual machine while the source workload is active; no application interruption is necessary
	- Cold cloning requires the application to be inactive; possibly the rate of data change is too rapid for the P2V to ever complete
	- There are many vendor and third-party tools to perform not just P2V but V2V and V2P as well
