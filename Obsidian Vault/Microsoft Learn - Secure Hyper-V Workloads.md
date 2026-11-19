<u>Objectives</u>
1. Describe the features and functionality of the HGS in Windows Server
2. Describe the attestation options available with the HGS
3. Describe shielded VMs, their creation, and their deployment

------------

- **Define Guarded Fabric**
	- *Fabric* - term applied to a collection of compute, network, and storage resources
	- *Guarded Fabric* - Hyper-V security solution that protects VMs against unwarranted inspection, theft, and tampering form either malware or malicious system admins. Consists of the following core concepts:
		- **Shielded VM** - trusted disk templates and images are specified within guarded fabrics, and VMs that use these templates are shielded
		- **Guarded Host** - servers that are specified as safe for hosting shielded VMs
		- **Host Guardian Service (HGS)** - ensures that only a safe and authorized guarded host can run a shielded VM. Also provides a safe and authorized guarded host with security keys to power on a shielded VM
	- *Tools used to automate and manage a guarded fabric*
		- **System Center Virtual Machine Manager (VMM)** - used as a unified management solution for virtualization hosts, virtual networking, and storage to help maintain a virtualized environment effectively
		- **Windows Azure Pack** - provides graphical web portal interface to manage a guarded fabric and shielded VMs
		- **Windows PowerShell** - used to create the components of a shielded VM and to provision a shielded VM to a guarded host
- **Define the HGS**
	- *HGS Attestation Service* - ensures that only a safe and authorized guarded host can run a shielded VM. Two attestation modes are available:
		- ***TPM-trusted attestation*** - guarded hosts are approved based on their TPM identity, measured boot sequence, and code integrity policies to ensure they only run approved code
		- ***Host key attestation*** - Guarded hosts are approved based on possession of a key
	- *Key Protection Service (KPS)* - provides a guarded host with the security keys required to power on a shielded VM, and for migrating a shielded VM to another guarded host
- **TPM-Trusted Attestation**
	- When a user starts a VM, the Hyper-V host sends the following three types of information to the HGS:
		- *TPM-identity* - host's unique TPM 2.0 endorsement key. HGS uses this information to check whether the host belongs to the list of HGS authorized hosts
		- *Measured Boot Sequence* - host sends HGS its Trusted Computing Group (TCG) log. This contains details about processes that were started during the most recent boot sequence, which the HGS compares to a known good reference to check the health of the host's hardware
		- *Code Integrity Policy* - host provides HGS with information about the Code Integrity (CI) policy that was applied on the host, which defines the binaries or executables that the host is permitted to run
- **Define KPS**
	- guarded hosts must obtain necessary keys from KPS before they are able to power on a shielded VM. Must provide the following:
		- *Health Certificate* - guarded host must obtain a clean certificate of health from the HGS Attestation service
		- *Encrypted Secret* - secret or Key Protector (KP) is encrypted using other secure keys that only the KPS knows. The KPS uses the encrypted secret to obtain the keys that are needed to unlock and power on a shielded VM
- **Key Features of Shielded VMs**
	- *Shielded VM Signed Template Disk* - basis for all future VMs deployed within the fabric. Provides additional security by hiding from the fabric administrators all confidential information, such as passwords and certificates
	- *Shielded Data Files* - encrypted file that contains encrypted secrets that are needed to deploy a shielded VM. Can only be read by a guarded host in trusted fabric, and specifies which guarded fabric the HGS can trust to host a shielded VM
	- <u>Shielded VM Deployment Process</u>
		1. Deploy an HGS server
		2. Set up a guarded host
		3. Prepare a signed template disk (.vhdx file)
		4. Create a shielded data file
		5. Import the shielded data file into the VMM library
		6. Create a new shielded VM from the signed template disk
		7. Add the shielding data file to the new shielded VM