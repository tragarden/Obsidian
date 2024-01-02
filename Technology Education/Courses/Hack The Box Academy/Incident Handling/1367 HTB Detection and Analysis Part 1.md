# Detection and Analysis Part 1

During the Detection and Analysis stage establishes focus on using applications and staff to log and sense attackers. 

Staff can look for abnormal behavior and actively seek out threats while automated applications like Endpoint Detection and Response ( #EDR), Intrusion Detection Systems ( #IDS), and Intrusion Prevention Systems ( #IDS) scan for threats. We can also rely on third-parties that scan for vulnerabilities. Hosting threat hunting activities for our staff can help detect threats as well.

#### Levels of Detection

We can focus on specific parts of the #network to compartmentalize our scans. We can consider a few common segments of networks:

- The network perimeter can be scanned using firewalls, #IPS / #IDS, and the #DMZ.
- The internal network is monitored with internal firewalls and host intrusion detection.
- The endpoints are protected with antivirus software and #EDR applications
- The applications can be monitored with logging of the application data and related services.

### Initiating an Investigation

Any time we identify an incident we should begin precursory investigations immediately so we know the context of the incident and can assemble the correct staff to address the issue. Do not draw to heavily on early assumptions, but use them as guidelines for your team members to be mindful of. 

Some important information to document during our investigations includes:

- Data and Time of the incident
- How was it detected?
- What happened during the incident?
- List the systems impacted
- Document any users with access to these systems
- Is this a recurring incident or a single case?
- Where did the incident occur?
- List the operating systems, IP addresses, hostnames
- Describe the current state of the system
	- If malware is present:
		- List of #IP addresses
		- time and data the #malware was detected
		- description of the malware
		- systems affected 
		- export the malicious files for forensic data collection

#### Incident Timeline

Creating a timeline of the incident is a useful way to track the sequence of events that lead to a successful attack. As each event or stage of the attack is identified, we should record this and begin listing the order of events chronologically. This will help us to see the path of the attacker as we discover the vulnerabilities that allowed them to gain unauthorized access. It is most important to note Time and Date, hostname of the affected device, description of the event, and remediation method.

#### Severity and Extent

Here is a list of questions we should ask to determine the severity and extent of the threat:

- What is the impact of this exploit?
- What are the requirements for this exploit?
- Does this exploit affect critical resources?
- What are the means of remediation?
- How many systems are the exploit present on?
- Is it a worm or virus with the capability to spread throughout our network?

### Related:

- [HTB Academy Home Page](https://academy.hackthebox.com/ 'HTB Academy home page')
- [HTB Academy D&A Part 1 Module](https://academy.hackthebox.com/module/148/section/1368 'HTB Academy D&A part 1 module')
