# Hardware Attacks

While many modern vulnerabilities are software-based, there are persistent hardware-based attacks that updating cannot remedy. Technologies like Bluetooth and Side-Channel attacks can compromise devices without mediation.

### Bluetooth Hacking

Bluetooth is a convenient short-range wireless communication method that is becoming more ubiquitous across all devices. This technology is vulnerable to attacks and increases the attack surface of any device that uses it.

Here are some of the many methods of Bluetooth exploitations:

| Method       | Description                                                                                                                              |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Bluesnarfing | unauthorized access to data via Bluetooth                                                                                                |
| Bluejacking  | sending of unsolicited messages via Bluetooth                                                                                            |
| Bluesmacking | Denial-of-Service attack that overwhelms Bluetooth connections                                                                           |
| Bluebugging  | gaining control of a device via Bluetooth connections                                                                                    |
| BlueBourne   | a set of vulnerabilities that enable attackers to control devices or install malware via Bluetooth                                       |
| KNOB         | Key Negotiation of Bluetooth where data encryption processes are manipulated during connection establishment.                            |
| BIAS         | Bluetooth Impersonation AttackS where vulnerabilities in the pairing process are exploited allowing attackers to impersonate the device. |

### Cryptanalysis Side-Channel Attacks

Cryptanalysis Side-Channel Attacks refers to information gained by running computer systems instead of brute-forcing or exploiting vulnerabilities.

- Timing Attacks - exploitation of the correlation between computation time of cryptographic algorithms and the content they are protecting.
- Power-Monitoring Attacks - evaluation of the data being processed by a device to determine the content of the data.

### Microprocessor Vulnerabilities

Microprocessors are complex pieces of hardware that have design and optimization strategies that create vulnerabilities. Spectre and Meltdown are two common vulnerabilities associated with microprocessors.

Mitigation strategies for microprocessor vulnerabiliites include:

- Retpoline - binary modification technique that prevents branch target injection.
- Compiler modifications
- Kernel Page Table Isolation ( #KPTI) isolates the kernel memory space from the user space.
- Microcode updates

Related:

[HTB intro to Hardware Hacking](https://academy.hackthebox.com/module/230/section/2469)