# Microprocessor Vulnerabilities

### Spectre

Spectre vulnerabilities were disclosed to the public in 2018 as CVE-2017-5753 and CVE-2017-5715, otherwise known as a bounds check bypass and a branch target injection. This was discovered by Jann Horn and Paul Kocher with collaborative efforts from Daniel Genkin, Mike Hamburg, Moritz Lipp, and Yuval Yarom.

Spectre breaks the isolation between applications and tricks them into leaking data by exploiting speculative execution techniques. This exploits the discarded incorrect predictions performed by the speculative execution module. The processor makes incorrect predictions, and when this happens the processor receives a false set of instructions from the attacker. These instructions modify the processor state which can load unexpected data into the cache. 

The compromised data cannot be directly accessed by attackers and they must use side-channel attacks to infer the data being imported into the cache.

### Meltdown

Meltdown was publicly disclosed in 2018 as CVE-2017-5754 by Jann Horn, Werner Haas, Thomas Prescher, Daniel Gruss, Moritz Lipp, Stefan Mangard, and Michael Schwarz. Meltdown disintegrates the isolation between applications and the operating system allowing malware to access program and operating system memory.

This attack is an exploitation of out-of-order execution standards of microprocessors. This standard enables instructions to be executed based on availability instead of sequence in an attempt to optimize resources and throughput. While the final execution order is correct, these out-of-order instructions are able to be observed by attackers even if they are rolled back. 

Meltdown induces an exception by attempting to access memory that it is not authorized to access. A problem with the out-of-order execution will allow this unauthorized access to occur. This would allow an attacker to export data from the unauthorized access into the cache for analysis via side-channel attacks. Cache timing attacks are most often used in these cases.

This is a critical vulnerability because it breaks isolation of the kernel allowing for infiltration and control of the kernel.

### Spectre vs Meltdown

- Spectre exploits Speculative Execution.
- Meltdown exploits out-of-order execution.
- Spectre breaks isolation between applications
- Meltdown breaks isolation between applications and the operating system.
- Spectre is more difficult to implement but more difficult to mitigate than Meltdown.

### Mitigation

There are both hardware and software based mitigation strategies for Spectre and Meltdown. The main goal is to block unauthorized access without inhibiting performance of the processor.

#### Retpoline

Retpoline is a mitigation strategy for Spectre that replaces hazardous indirect software branches to prevent speculative execution by Spectre.

Indirect Software Branches are program instructions that guide the execution path.  In a direct branch, the path is pre-determined. Indirect branches have dynamic pathing that change depending on circumstance.

Retpoline avoids speculative execution when encountering indirect branches. It redirects the program flow which imposes a performance overhead in programs that use indirect branching.

#### Compiler Barriers

Modifying the compilers that generate code by implementing barriers is a method of mitigating Spectre. 

Memory Barriers, also known as Fence Instructions, monitor loading and storing of memory and make sure they are completed before the barrier. They maintain consistency of operation and prevent unintentional reordering of memory access by either the compiler or processor.

Branch Prediction Barriers preveny speculative execution at certain points in code that could cause vulnerabilities. They limit the prediction of branches.

These barriers control the flow of execution by disallowing the processor to execute in a speculative way.

#### KPTI

Kernel Page Table Isolation ( #KPTI) is the primary way that Meltdown is mitigated. It does so by isolating the Kernel Page Tables to prevent memory leakage from the kernel. This method can slow performance of processors by increasing context switch times.

### Microcode Updates

Microcode Updates implement granular control and restrictions on speculative execution in the processor. The operating system applies strict methods to prevent vulnerabilities within the hardware. 

These vulnerabiliites highlight the sacrifices in security associated with higher performance.