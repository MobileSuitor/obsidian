<u>Objectives</u>
- Identify and differentiate between a Type 1 and Type 2 hypervisor
- Understand how Type 1 and Type 2 hypervisors interact with server hardware to create virtual machines
- Awareness of the open-source KVM hypervisor
- Discover the function of virtual machine files
- Understand the advantage of using snapshots

------
- **Type 1 Hypervisor** - AKA 'bare metal' hypervisor, sits directly between the hardware and the VM. Needs a <u>management layer</u> for users to be able to interact with the hypervisor (sort of like an OS)
- **Type 2 Hypervisor** - AKA 'hosted hypervisor', needs to be installed on top of the existing host OS, and as such depends on the OS for access to hardware resources
- **KVM (kernel-based virtual machine)** - built-in module of the Linux kernel that turns it into a type 1 hypervisor
- **Snapshots** - preserves the state of a VM, allowing you to return to the same state repeatedly
 
# Table 1 - VM File Types

| **File Type**        | **Filename**    | **Description**                                                       |
| -------------------- | --------------- | --------------------------------------------------------------------- |
| Log file             | \<vmid>.log     | Records VM activity                                                   |
| Virtual Disk (QCOW2) | \<vmid>.qcow2   | Compressed disk image format<br>that supports snapshots               |
| Virtual Disk (RAW)   | \<vmid>.raw     | Flat, uncompressed disk image,<br>faster performance at cost of space |
| Configuration File   | \<vmid>.conf    | Stores VM hardware and system settings                                |
| Backup File          | \<vmid>.vma.zst | Includes both VM disk and config                                      |

