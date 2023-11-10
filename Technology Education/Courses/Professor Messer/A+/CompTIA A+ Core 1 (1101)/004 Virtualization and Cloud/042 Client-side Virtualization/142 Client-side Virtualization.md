# Client-side Virtualization 4.2

### Virtualization

#Virtualization is when you **use multiple operating systems on one computer**.  This was created by #IBM in 1967 and simulates multiple computers with seemingly independent hardware – but all sharing the same set. 

Virtualization solves some problems like **using older OS’s that are incompatible with modern systems**.  You can also run multiple versions of multiple OSs simultaneously.

### Types of Virtualization

*Cross-platform virtualization* refers to **running multiple incompatible OS’s**, mainly #Linux, #Mac, and #Windows.   You will be able to use all three **simultaneously without partitioning drives** or rebooting. 

The #Hypervisor is a **manager for virtual machines and hardware** management.  This may require a special #CPU that supports virtual machines. 

#Intel has *Virtualization Technology* ( #VT), and #AMD has #AMD-V.   Virtualization consumes a lot of #RAM and twice the memory of the default #OS. 

*Sandboxing* allows us to **create a testing environment without consequence**.  You can develop and deploy within the sandbox, experience catastrophic failures, and then reset the production system like nothing happened.

### Characteristics

*VM escaping* is **when #malware recognizes that it’s on a virtual machine** and could theoretically capture control of the hypervisor, allowing the malware to spread across more machines.

With Virtual Machines, all **guests are self-contained systems that have their own security measures** and software.  These can be managed as you would any non-virtual system. 

Attackers will try to bait you into using their virtual machines on your system.  ***Any time you accept an invitation to deploy a virtual machine on your own hardware – you accept uncertain risks***. 

*Shared network address* means the **virtual machine has the same #IP as the host computer**.  The VM will use a private IP address within its own systems and uses #NAT to convert to the host IP.

*Bridged network access* is **when the VM is a physical device** on the same network.

*Private addressing* just lets you keep the **VM contained within the virtual network**.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/client-side-virtualization-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [031 Troubleshooting Solutions](031%20Troubleshooting%20Solutions.md)
- [051 How to Troubleshoot](051%20How%20to%20Troubleshoot.md)

#study #professormesser #comptia #Aplus #sandbox