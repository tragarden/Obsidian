
# Incident Report Elements

### Executive Summary

The Executive Summary provides an overview of the incident and outlines our findings, actions, and the impact in a way that appeals to a broad audience from laymen to experts. This is one of the most important aspects of our reporting as it will be seen by the largest group of stakeholders. 

The Executive Summary can be broken down into the following categories:

| Section            | Description                                                                                                             |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Incident ID        | Unique incident identifier                                                                                              |
| Overview           | A summary of the type of incident with estimated time and date, duration, list of affected systems, and current status. |
| Findings           | A compilation of enumeration results and details about the data affected.                                               |
| Actions Taken      | Details about the immediate response measures and if third party organizations are involved.                            |
| Stakeholder Impact | A summary of the ramifications and repercussions that occurred as a result of the incident.                                                                                                                        |
### Technical Analysis

A thorough technical description of the events of the incident that addresses the following key factors:

#### Affected Systems

Outline the systems and data that were affected and compromised by the incident, as well as the volume of data that was either compromised or exfiltrated.

#### Evidence Analysis

Describe the analysis performed and the evidence that was identified and evaluated. Maintaining the integrity of the evidence is as crucial as it would be during a criminal investigation. It is a common and useful practice to hash and encrypt the evidence in a way that secures it from tampering or loss.

#### Indicators of Compromise (IoCs)

Indicators of Compromise ( #IoC) identify compromises within the organization and extending into other organizations in some cases. Identifying unusual activity like outbound traffic or processes can help connect the incident to a specific group or attacker.

#### Cause Analysis

Determining the root cause of the incident identifies the underlying reasons for the incident.

#### Timeline

It is important to construct a timeline of events that include the following information:

- Reconnaissance
- Initial Compromise
- C2 Communications
- Enumeration
- Lateral Movement
- Data Access
- Data Exfiltration
- Malware Activity and Deployment
- Process Injection 
- Process Persistence
- Containment Times
- Remediation Times
- Recovery Times

#### Nature of Attack

Identify the type of attack, tactics used, and procedures ( #TTP) used in the incident.

### Impact Analysis

Evaluate the range of affect and consequences of the incident. You need to quantify and qualify the extent of damage caused and identify the systems, processes, and data that has been compromised. This includes financial losses, changes to reputation, and regulatory penalties. 

### Response and Recovery

A chronological report of the incidents, mitigation methods, eradication methods, and restoration to normal operation must be given to outline what has happened in an organized way. 

#### Immediate Response

##### Access Management

- Identification of Compromised Items
- Timeframe
- Revocation Methods - detail the technical methods of disabling accounts, and hardening permissions and firewall rules.
- Impact

##### Containment Strategy

- Short-term - immediate actions taken to isolate the incident from the network. 
- Long-term - future preventative measures like network segmentation or zero-trust architecture implementation.
- Effectiveness - how will these measures limit incidents in the future.

#### Eradication Measures

##### Malware Removal

- Identification - using Endpoint Detection and Response ( #EDR) tools to identify #malware.
- Removal Techniques - what removal tools were used?
- Verification - using #checksum verifications or #hueristic analysis.

##### Patching

- Identifying Vulnerabilities - listing #CVE identifiers.
- Managing Patches - describe the patching process including tests, deployment, and verification.
- Fallback Procedures - steps to restore the system to a previous state.

#### Recovery Steps

##### Data Restoration

- Backup Validation 
- Restoration Process - how was data restored and decrypted?
- Checking Data Integrity 

##### System Validation

- Security Measures - updating and reconfiguring firewalls and Intrusion Detection Systems ( #IDS).
- Operational Checks - confirm that our systems will be operational per the production environment.

#### Post-Incident

##### Monitoring

- Monitoring Plans - detecting similar incidents in the future before they occur.
- Technology and Tools - what monitoring tools were used?

##### Takeaways

- Gap Analysis - identify the security measures that failed.
- Recommendations - a timeline and priority list of recommendations before implementation.
- Preventative Measures - needed changes in policy, network structure, and personnel training. 

### Diagrams

- Incident Flowchart - illustrate how the attack propagated throughout the network.

- Map of Affected Systems - network topology that is color-coded with annotations.

-  Attack Vector Diagram - flowchart using arrows and annotations to visually depict the attack route.

### Appendices

A collection of raw data and artifacts that add context, evidence, and technical information to help experts understand how the incident was executed. This is a very important part of the report that constructs the main body of the incident report.

- Log Files
- Pre-incident Network Diagram
- Post-Incident Network Diagram
- Forensic Evidence
- Code
- Incident Response Checklist
- Communication Records
- Legal and Regulatory Documents
- Glossary with Acronyms

### Best Practices

- Cause Analysis

- Community Sharing - distribution of non-sensitive information for the defense community. 

- Updating with Regularity - keeps the stakeholders informed and aware of the state of the incident.

- External Review - validate findings through third parties. 

### Related: 

- [HTB Academy Home Page](https://academy.hackthebox.com/ 'HTB Academy Home page')
- [HTB Academy Elements of Incident Reports](https://academy.hackthebox.com/module/238/section/2581 'HTB Academy elements of incident reports module')