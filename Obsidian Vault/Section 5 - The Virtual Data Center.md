<u>Objectives</u>
1. Identify the components of a software-defined data center; the hypervisor, management server, management interface
2. Understand the advancements in efficiency server, storage, and network virtualization provides for data centers
3. Awareness of the Proxmox hypervisor and Proxmox VE management interface
4. Understand the functionality of virtualized storage pools and data stores and how they provide scalable storage for VMs
5. Identify the logical components of a virtual network
6. Learn the types of virtual networks
7. Understand virtual data center enablement of cloud
8. Understand the importance of hypervisor security
------------------
<u>Key Terms</u>
1. **KVM** - kernel-based virtual machine; open-source hypervisor technology which is available on Linux OSs
2. **Central Management Server** - server that coordinates and manages servers across a virtual data center
3. **Web-Based Management Interface** - dashboard administrators use to interact with the virtualized data center environment
4. **Virtual Data Center** - data center where physical data center components have been virtualized
5. **Management Layer** - software that acts as the control center for all virtual components and resources across the physical and virtual data center infrastructure
6. **Bridged Network** - type of virtual network where both a VM and its host are connected to the same network by connecting to the host's NIC to the VM's vNIC. VM shares IP with host
7. **Network Address Translation (NAT) Network** - type of virtual network where a VM is connected to a private network on the host called a virtual machine network (VMnet). VM uses host IP address, which is then translated and forwarded to the VM's private IP address on the VMnet
8. **Port Forwarding** - virtual networking feature that enables incoming web traffic to pass through a specific port. This allows IP addresses on a VMnet to be translated and connected to an external network
9. **Host=only Network** - similar to NAT network, but without IP address translation. Restricts access to only the private network, preventing connection to external networks
-----------------------

- 