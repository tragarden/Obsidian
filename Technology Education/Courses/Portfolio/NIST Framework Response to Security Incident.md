### Overview

You will analyze a situation using the National Institute of Standards and Technology's ( #NIST) Cybersecurity Framework ( #CSF) to create an incident report. This voluntary framework provides a set of standards, guidelines, and best practices for managing security risks and build trust within an organization. The CSF is designed to be scalable and applied to many different contexts.

### Scenario

You work for a multimedia company that offers web design services, graphic design, and social media marketing solutions for small businesses. Recently this organization experienced a DDoS attack that compromised the local network for two hours. It caused services on the network to stop responding due to an ICMP flood attack preventing normal network traffic from accessing internal resources. The response from the security team was to block incoming ICMP packets, stopping non-critical offline network services, and restoring these services when possible. 

When the security team performed an investigation they found that the event was caused by a threat actor flooding the network with ICMP pings through an unconfigured firewall which overwhelmed the network through a Distributed Denial of Service ( #DDoS) attack.

To address this incident the security team implemented the following changes:

- New firewall rules to rate-limit inbound ICMP packets.
- Source IP verification via firewall to analyze spoofed IP addresses on ICMP packets.
- Network monitoring software was installed to detect unusual or suspicious network traffic.
- IDS/IPS is now used to filter out ICMP traffic based on suspicious patterns.

Apply the five NIST CSF framework principles to the incident:

- IDENTIFY security threats via auditing of systems, local network, devices, and access privileges.
- PROTECT internal assets via policies, procedures, training, and tools to mitigate threats.
- DETECT security incidents and improve monitoring to improve efficiency of detection.
- RESPOND by containing, neutralizing, and analyzing incidents and improve the process.
- RECOVER affected systems to normal operational standard and restore all assets.

### Work

#### Identify 

The security team recognized network failure for two hours due to a DDoS attack that utilized  ICMP flood methods to overwhelm the network hardware. Eventually network services stopped responding to the heightened demand from ICMP pings which inhibited normal network traffic and prevented users from accessing internal resources. This prevented employees and customers from accessing assets and internal resources provided by the company.  

#### Protect

The security team implemented net firewall rules that limit the rate of incoming ICMP packets to prevent the network from being overwhelmed. The firewall was additionally configured to verify source IP addresses in order to detect spoofed IP addresses on the inbound ICMP packets. IDS / IPS solutions have been implemented to use pattern recognition to identify suspicious network traffic and identify unusual ICMP activity. Network monitoring software is now being used to observe network traffic and provide alerts to the network administrator.

#### Detect

Firewall, IDS, IPS, and network monitoring applications will work in conjunction to observe network traffic and alert the network administrator to suspicious activities and patterns. 

#### Respond

The threat to the network was contained via firewall rules and all staff will be notified and educated on the attack. Customers will be informed about the downtime with an explanation about what happened and the nature of the attack. Improved and continuous monitoring of the network will be implemented to prevent these attacks in the future. A playbook will be created for procedures and processes related to this attack to instruct the security team on more efficient and fast remediation of this type of attack.

#### Recover

After implementing appropriate security monitoring and prevention methods the network was restored to normal operation. Customers and staff have been informed of the attack and notified that the network is now back to normal operation standards. Any missed information from customers has been requested and the team will work manually to restore this data. Staff will be notified of the development and publishing of the new playbook so they can become educated on this subject with proper procedures and processes.