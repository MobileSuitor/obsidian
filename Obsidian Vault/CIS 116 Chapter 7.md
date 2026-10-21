<u>Objectives</u>
1. Understand how VMs use CPU resources
2. Configure CPU resources in a VM
3. Examine some CPU tuning practices
4. Understand how hyperthreading works with virtualization

-------------

- **Scheduling Time on a CPU** - virtualizing a CPU is actually the hypervisor scheduling slices of time on the physical CPU. vCPUs can roughly be mapped to a single physical core
	- When sizing a virtualization host, since a single CPU is not 100% busy, one CPU can service multiple vCPUs
- **Multiprocessor Virtual Machines** - a VM with multiple vCPUs needs to schedule time on multiple CPUs. Additional vCPUs might hinder performance depending on many factors including physical resources and CPU contention. Best practice is to configure one vCPU to a new VM and increase the number if needed.
- **Hyperthreading** - Intel technology that provides better CPU utilization (AKA Simultaneous Multi-Threading for AMD). Provides up to an additional 30% of performance per CPU, though it appears to double the amount of CPUs