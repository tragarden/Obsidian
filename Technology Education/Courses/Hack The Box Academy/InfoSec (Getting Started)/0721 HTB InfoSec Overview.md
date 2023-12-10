# InfoSec

Informational Security ( #InfoSec) covers a wide range of security topics related to networks, infrastructure, applications, system audits, security testing, continuity, digital forensics, and incident response.

InfoSec can be thought of as protecting data from attackers proactively, actively, and post-incident. The scope of this is beyond software, including operating systems and their functions, as well as physical aspects such as hardware and documents.

### Risk Management Process

There are five steps to the process of managing vulnerabilities that begin with discovery and resolve with removal and monitoring. These steps are:
1. Identifying any risks while considering the many facets of the organization. 
2. Analyzing the identified threats and estimating the potential damage and reach of the threat.
3. Evaluation of threats includes prioritizing the most dangerous items and determining a method of removal and future mitigation.
4. Implement the evaluation plans and removing or managing the risks within the organization. 
5. Once the risks are removed, continue to monitor and mitigate with preventative measures. 

### Teams

Red team members are the offensive agents that simulate and execute attacks on the target to determine vulnerabilities and flaws in security. These are known as pentesters, or alternatively known as security assessors. 

Blue team members are the defensive agents that design the security layout and implement preventative measures and mitigation techniques.

### HyperVisor

A #Hypervisor is software that allows you to use the hardware on your machine to run Virtual Machines ( #VM) in an isolated environment. This is useful because we can attempt to exploit and pentest these machines in isolation so that no harm befalls our actual devices.

Common hypervisors include #Windows #Hyper-V, #Proxmox, #VMware, and #VirtualBox. Proxmox and VMware ESXi are examples of "bare-metal" hypervisors - meaning that they are directly installed onto the hardware of your dedicated machine.

### ISO

An Optical Disk Image ( #ISO) is essentially a #CD-ROM file that is mounted to your hypervisor to simulated disk install of the #OS. ISO images can be customized to a great extent and allows for very specific setups for pentesting.

### OVA

An Open Virtual Appliance ( #OVA) is an OVF #XML file that determines the configuration of your VM and it's associated #VMDK. The VMDK is virtual disk that the operating system is installed upon. 