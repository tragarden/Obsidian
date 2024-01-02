# Containment, Eradication, & Recovery

### Containment

Containment means mitigating further damage by containing any damage and locking the systems and applications that were exploited. These systems must be contained or locked simultaneously - meaning that if these systems are not all secured at the same moment, the attacker can recognize that they have been detected and will still have the ability to act on anything we haven't disabled.

#### Short-term Containment

Short-Term acts of containment act quickly to deter any further exploitation while leaving the smallest trace possible that anything has changed. Actions during this phase include isolating systems via #VLAN, unplugging ethernet cables, and taking forensic images of the system. The goal is to prevent the attacker from further exploiting our systems while maintaining them for our incident research purposes.

#### Long-term Containment

Long-term acts of containment include changing passwords, increasing #firewall security, activating a Host Intrusion Detection System ( #IDS), patching or updating systems, and shutting them down once the previous steps have been completed.

### Eradication

The Eradication stage removes the root causes for the incident and any artifacts of the attack. This can be achieved by removing #malware, reconstructing systems, reconfiguring systems, and restoring them from backups. Hardening our systems as well as patching and updating them should be performed during this stage as well.

### Recovery

The Recovery phase is a long and ongoing stage after we have detected and removed threats from our systems. We need to restore the system to an improved state of function with increased logging and monitoring for unusual logons, processes, or changes to the registry. This may take several months, but this is required because this system will likely be the target of another attack since the attacker is already familiar with this system.

### Related:

- [HTB Academy Home Page](https://academy.hackthebox.com/ 'HTB Academy home page')
- [HTB Academy 1369 Containment Eradication Recovery Module](https://academy.hackthebox.com/module/148/section/1369 'HTB academy module for this note page')