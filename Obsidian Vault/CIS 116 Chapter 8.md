<u>Objectives</u>
1. Understand how memory is virtualized in a VM
2. Understand the memory configuration options
3. Investigate memory tuning practices
4. Examine some memory optimizations

-----------

- **Virtualizing Memory** - VMs use memory the same way as traditional computers, as really fast storage and workspace for OSs and programs. Hypervisors map virtual memory blocks to the physical memory and uses address translation tables to keep track (part of the hypervisors overhead)
- **Memory Pages** - memory blocks are also called pages. *Paging* is when pages move from memory to disk, but involves disk I/O and is therefore slow. 
- 