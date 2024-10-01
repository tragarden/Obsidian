# Report Types

While Internal Penetration Test Reports will be the main focus throughout this course, there are a variety of report types that you will likely encounter throughout a career in technology.

There may be examples of external penetration test reports throughout this course, but mostly this will be avoided. OSINT data and other publicly available information will be omitted as well like email addresses, subdomains, credentials, domain ownership, and other externally obtained data.

Information that will not be covered in this course include:

- Public DNS information
- Email Addresses
- Domain Ownership Records
- Subdomains
- Vendors
- Related Domains
- Cloud Resources

### Assessment Types

There are various assessments that will be covered throughout this course:

#### Vulnerability Assessment

Vulnerability Assessments require running automated scans of a given environment to enumerate any vulnerabilities present, which may be authenticated or unauthenticated. NO exploitation will be performed during this assessment, but results will be examined to demonstrate to the client that potential vulnerabilities exist. 

Validation is the only objective of this assessment type and culminates in a confirmation of vulnerable version states, known misconfigurations, and evidence for possible lateral movement and escalation. At times, clients will ask for scan results without validation.

#### Internal vs External

External scans are performed from the perspective of an outsider anonymous user that only has access to the network through external methods of entry.

Internal scans are performed from the perspective of anonymous users that are operating from within the network so that internal network elements and hosts can be investigated from behind the firewall. This type of test may even be performed with credentials provided by the client. These test will be more extensive and produce more accurate and plentiful results.

#### Report Contents

The report will reveal themes and correlations observed during the testing, focusing on found vulnerabilities and patterns related to procedural deficiencies.

### Penetration Testing

Penetration Testing is not limited to automated tools and scans and with permission from the client, can lead to exploitation and payload implementation. Similar to vulnerability scans, penetration testing can be performed internally or externally.

- Black box testing is an external test where no information is provided by the client.
- Gray box testing provides a scope of IP addresses and CIDR ranges.
- White box testing may provide credentials, source code, configurations, and more.
- Zero Evasion tests reveal as many vulnerabilities as possible.
- Hybrid Evasion means scanning with increased aggression until the tester is observed by the monitoring systems and agents that work within the network. Usually once detected, the test will continue on as non-evasive. This type is useful for identifying weaknesses in monitoring and defensive systems.
- Evasive Testing means the tester will attempt to remain undetected for as long as possible to determine access levels that can be obtained discreetly. These tests are often longer and ongoing to simulate a real attack that is performed covertly over time. This is usually performed on organizations with a mature security posture.

#### Internal vs External

External tests are performed from the perspective of an outside anonymous user using OSINT data and public information to infiltrate the network. 

Internal testing is performed as an anonymous user on the internal network or an outright authenticated user with access to resources. This is performed to find as many flaws as possible with horizontal and vertical privilege escalation that can compromise the entire network.

### Inter-Disciplinary Assessment

Sometimes a team with a diverse set of skills will be used to perform penetration tests. Theses are complex and collaborative test between a team and client.

#### Purple Team Assessments

This is a combined effort from the red and blue teams and are typically composed of a penetration testers and an incident responder. A threat is simulated by the penetration tester and the incident responders work within the blue team to monitor this attack and respond accordingly.

#### Cloud-based Testing

This shares many similarities with traditional penetration testing and may just be an extension of the typical penetration test. This is often done in collaboration with a team member that has extensive understanding of cloud technology and administration methods, who conveys this knowledge to a penetration tester while they are performing their work.

The helper will help the penetration tester understand more nuanced concepts like containers and serverless apps, which are different from traditional networking infrastructure. These advents require a totally different set of tools and understanding than traditional network components. The helping member will often need to be involved in the reporting for this type of test.

#### IoT Testing

IoT networks are typically composed of three main components: a network, a cloud, and applications. Typically a specialist member of the team will work with a penetration tester to supplement the testers basic understanding of these systems. The hardware layer of these systems is often tested. During the reporting phase, the tester will work with the IoT expert to write about the IoT related details of the report.

#### Web Application Testing

Most of the time the testing of web applications deals with the application itself and not the server that hosts the application. At times, the client may request that the related infrastructure be evaluated along with the application, which means infiltrating the application in order to perform potential exploitations on the server itself. This might mean escalating privileges through the Active Directory or other authentication system.

#### Hardware Penetration Testing

Hardware testing is most often performed on IoT devices but in certain cases may extend to the hardware components of devices with physical components like laptops, kiosks, and ATMs. Rules of Engagement ( #RoE) must be established before these devices can be ethically tested as the testing may result in the destruction of the device or device components. In extreme cases, this might mean desoldering chips from motherboards, although this is rare and unlikely.

### Draft Report

In modern reporting the client will often expect to have a dialogue about the report so their feedback can be incorporated. They may want to address each individual finding and add their own comments to the report before it is finalized. In many cases they will review a draft and request the removal of any inflammatory language and change the order in which the report is presented.

It is common practice to provide a draft for client review before a finalized version is created. This allows the client to ask questions, request clarification, and explain their expectations. This is useful to us because it allows us to make the report as valuable as possible to the client. Oftentimes the client input is to ensure that the report is palatable to their board of directors or company executives in their pursuit of more funding or permission to increase security posture.

### Final Report

After the draft report has been collaboratively evaluated by the client and penetration tester, the final report will be written with the requested modifications. This is often necessary as auditors will often not accept a draft until it conforms to their compliance obligations.

#### Post-Remediation

In many cases a client will request that aspects of the penetration test be repeated after they have observed results of the first tests. This is very common among organizations that are working within a set of compliance and regulatory standards. While some testing is repeated, DO NOT repeat the entire penetration test or assessment. Only reevaluate the findings and hosts that the client noted during their review of the draft report.

Possible consequence that may result from avoiding reassessment:

- A client asks for a remediation at a later date and the original environment has undergone so many changes that a direct comparison cannot be made. The second set of tests provide a point of comparison.

- If new hosts have been introduced, this may result in a loop of remediation where new hosts are continuously tested.

- If the environment has changed, you will discover that the vulnerability assessment will have a new scope and new vulnerabilities will be found in dramatic fashion.

- A Breach and Attack Simulation ( #BAS) can be suggested to the client, where the penetration test is automated and those scenarios are periodically performed to test the network.

### Attestation Report

Clients may request an Attestation Letter otherwise known as an Attestation Report. This is a report that is suitable for third-parties like vendors and customers who need evidence that a penetration test has been performed. This Attestation report acts as an auditable account of the tests performed without including the sensitive technical details of the penetration test. This can be derived from a stripped down version of the final report that removes screenshots, discovered credentials, and vulnerabilities discovered during the testing process. This report will tell the amount of findings, methodology used, and comments about the network environment. This will be a much shorter report, typically being one to two pages in length.

### Deliverables

There are other items that may be requested by the client in addition to a draft and final report.

#### Slide Deck

A slide deck is a slide based presentation that can be attuned for several audiences with different levels of understanding. Language and reporting should be different for each presentation, paring down technical findings for more laymen audiences. These reports will present technical findings in charts and graphs that are easily interpretted by the audience. Including some personal anecdotes from the testing procedure or correlating recent current events to the threats posed to the organization are ways to keep the audience engaged and relate the content to them. Creating a relatable report that holds your audience's attention is the goal with Slide Deck reporting.


#### Spreadsheet of Findings

This is a list of all fields from your report in the form of a spreadsheet or series of sheets. This allows for the recipients to sort and manipulate the data easily. They may be able to import this spreadsheet into their in-house ticketing systems for internal reporting and tracking. This document WILL NOT contain an executive summary. The main purpose of this document is to sort findings by severity and category for remediation prioritization. Learning how to create useful and intuitive pivot tables is advised when creating this type of report.

### Vulnerability Notifications

If a critical flaw is discovered during your testing, sometimes it is required that you end the testing immediately and inform the client of the issue so they can determine if they want to address the issue immediately or wait until you complete all assessments.

#### When to Notify

You should immediately notify your client of any vulnerability that is directly exploitable and exposed to the internet when the threat is exposed to remote code execution, data exposure, or leveraging of weak and default credentials. Beyond these extreme cases, the notification of client should be determined during the kickoff session to imply a baseline of concern and action. Tell the client what they may expect from the assessment and ask them what they want to be alerted about.

When notifying clients about threats in this manner, reduce all extraneous information, provide a cut and dry explanation of what is at risk, and give the organization the tools and methods for reproducing the threat for their own team.

### Resources:

- [HackTheBox Home Page](https://academy.hackthebox.com/ 'the home page for hack the box')
- [HTB 1538 Types of Reports](https://academy.hackthebox.com/module/162/section/1538 'the page for this hack the box module 1538')
