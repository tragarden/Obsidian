# Report Components

The final report is the main item that clients are paying for when they pay for a penetration test or vulnerability assessment. This is where skills are demonstrated and the organization values the report above all other acts. The report needs to be purposeful and free of unnecessary information and fluff so that the reader doesn't become overwhelmed with a flood of information.

### Priorities

When writing a report there are many factors that only clutter the report and have little impact on the audience. Understanding tools used and the output from tools is important for pruning out the extraeneous information that we shouldn't be included in the final report. The report should have repeatable processes, sorted and processed data, and removal of false positives and data that doesn't illustrate clear points.

Illustrating key issues like Remote Code Execution ( #RCE), sensitive data leaks, and major vulnerabilities is what a client is looking for. These are notable and memorable to the laymen audience. 

### Attack Chain Structure

When describing an attack chain, there should be a main summary that described the objectives of the penetration tester and the methodology behind their approach. It should describe what the tester did in a general way that can be understood by the audience. After the summary should be a list of the steps taken to achieve the assessment:

1. Using Responder to obtain NTLMv2 password hashes for a user.
2. Using Hashcat to crack the password offline in cleartext. This allowed the tester to access the local domain without elevated privileges.
3. Using BloodHound to enumerate the domain and create visual representations of attack vector pathing. Multiple privileged users were discovered with Service Principal Names ( #SPN) that were used to perform Kerberoasting to retrieve TGS tickets. These were cracked offline via Hashcat.
4. Using GetUserSPNs.py against the mssqlsvc account to gain local administrator rights on the host domain.
5. Passwords are successfully cracked offline in cleartext.
6. Gaining authentication to the local domain via cleartext passwords from the host registry by decrypting LSA items from an autologon account.
7. Account with local administrator rights was accessed to gain Kerberos TGT tickets for a given user. This user was part of an admin group that allowed the tester to gain DCsync rights on the domain. NTLM hashes were retrieved compromising the domain via Golden Ticket.
8. Using Rubeus to extract Kerberos TGT tickets for a user and performing a pass-the-ticket attack to gain authentication.
9. Using DCSync attack to authenticate their accound via Mimikatz, thus compromising the domain.

#### Attack Chain Screenshots

Following this shortlist of steps would be screenshots from each tool used, showing the commands and processes used for each step. This allows the in-house staff to follow along with each step of the process to see how their domain was infiltrated, allowing them to respond to the attack in their own time as they mitigate and remedy these attack methods.

This section would include the screenshots from tools with a small explanatory paragraph in the following order:

- Responder - captures the password hash.
- Hashcat - cracks the password hash to reveal cleartext password.
- GetUserSPNs - enumerates accounts with SPNs for Kerberoasting, retrieving NTLM hash.
- BloodHound - enumerates the AD for users, groups, ACLs, properties, sessions, admin access, and possibly more information.
- GetUserSPNs - accessing accounts to perform Kerberoasting.
- Hashcat - admin password hash is cracked to reveal plaintext password.
- CrackMapExec - password used to gain remote access and retrieve more cleartext passwords.
- Remote Desktop Protocol ( #RDP) - logging in remotely as an admin.
- DCSync - used to steal Active Directory passwords from a database by leveraging protocols for the Domain Controllers.
- Rubeus - used to view available Kerberos tickets for the admin user account.
- Rubeus - a pass-the-ticket attack is performed to access domain resources.
- Cached Kerberos Ticket - gaining access to an admin session via cached Kerberos tickets.
- Mimikatz - retrieves the NTLM password hash for default administrator account with Enterprise Admin access to the domain.
- CrackMapExec - authenticates the Domain Controller in the local domain.
- SecretsDump - retrieives all NTLM hashes for the domain and performs password analysis.
- Hashcat - cracks the new password hashes showing metrics.

### Writing the Executive Summary

The Executive Summary is the most important deliverable related to the final report and demonstrates the weaknesses in a network and the methods for exploiting them in a way that can be reproduced by the organization. This report will be viewed by the stakeholders such as the IT and Security teams, Internal Audit department, Executives, and the Board of Directors.

This part of the report validates your findings so that the aforementioned groups can request more funding or validate past budgets. This part of the report must be understood by an audience without technical understanding.

#### Key Concepts

This report will be reviewed by the people that are responsible for determining the budget for fixing the discovered issues. Please consider the following ideas when writing this summary.

- Addressing a non-technical audience - if your parents couldn't understand this part, you did it wrong.
- Remember that the audience has no familiarity with tools used or attack concepts.
- This might be their first penetration test and first time receiving a report about one.
- They will likely have a short attention span for this topic. Keep their attention.
- No one in this audience wants to have to Google terminology.

#### Do

- Be specific when citing metrics. Avoid vague terms like 'many' and 'few' and cite specific numbers.
- Keep this part of the report limited to about 1.5-2 pages. Anything beyond this amount is likely too verbose for the audience in question.
- Describe accessed resources in terms they understand. Avoid language like 'we infiltrated the local domain and gained access to financial credentials' and say things like 'we were able to view bank statements or HR records'.
- Decribe mitigation methods that are practical. Do not prescribe scheduled services or a set schedule - tell them the security team needs the tools and resources to perform these tasks and create their own schedule.
- Provide expectations for how much effort will go into the needed changes. If you have an understanding of the amount of internal politics these groups will work through, set expectations for the time needed to complete fixed in terms of low, medium, and high.

#### Do Not

- Do not name specific vendors. Recommend the general contractors needed to perform tasks but do not cite company or tool names. If you decide to make a suggestion, insist that they should consider alternatives and not run with your suggestion.
- Do not use acronyms. Your audience will not know what SMTP or NTLM is.
- Do not talk about issues that are not of impact to the organization.
- Do not use terminology they are unfamiliar with. 
- Do not reference the more technical aspects of the report. Spare the technical details as they may not understand them or have time for them.

#### Vocabulary Changes

Vocabulary modification will likely be necessary when writing to a non-technical audience. When you want to use an acronym or advanced term, try considering the following adaptations:

- VPN / SSH - lets administrators work remotely.
- SSL / TLS - secures web browsing.
- Hash - validates file integrity with a common algorithm.
- Password Spraying - spamming popular passwords in an attempt to gain access.
- Password Cracking - converting passwords from encrypted info to plaintext.
- Buffer Overflow or Deserialization - remote access to a device.
- OSINT - finding data online about a company.
- SQL Injection / XSS - using input fields to manipulate site code.

#### Considerations

To illustrate the strengths an organization has, point out areas where you found no problems. If all hosts are regularly updated, inform the executives that the system admins are doing an excellent job of patching units. This will endear you to the sysadmin team and hopefully the executives will reward them (they won't).

Avoid language that makes it seem like they have done nothing or have failed at doing something. If configuration is weak and needs improvement, avoid saying 'the team needs to begin configuring devices' and instead say that 'the team needs to continue configuring devices and refine their processes for doing so'.

### Recommendations Summary

The Summary of Recommendations or the Remediation Summary contains a list of short, medium, and long-term recommendations the organization can take to improve their security posture based on their current position. Using information about their budgets, business, and staff requirements can help you make accurate recommendations for improving over time.

Try to include a true priority queue for them and remember the phrase: 'when everything is important, nothing is important'. Relate the specific findings back to each recommendation. Advise them on best practice recommendations that can help them eliminate problems in the future. Encourage them to improve their baselines and standards. Offer generalized solutions like 'improving patch management procedures' that can help them identify weak points while still improving security posture. This will allow the team that manages patching to be involved in the process of change.

### Additional Components

After the executive summary is written, the rest of the report components described below.

#### Findings

The Findings section shows off the work of the penetration tester and illustrates the current state of the organizations network environment. This section helps the technical teams see the flaws in their current environment and reproduce steps to alleviate them.

### Appendices

Some appendices will be in every report while others will be presented only when required by circumstance. We can refer to these as static and dynamic appendices.

#### Static

These are required for every written report.

##### Scope

This shows the defined scope of the assessments performed including IP and CIDR ranges, URLs used, facilities, devices, etc.

##### Methodology

This shows the repeatable processes and demonstrate that your process makes sense and follows a set structure.

##### Severity Ratings

This section would include CVSS scores but in the case that these do not apply to the assessments, you will need to explain why you rated each item of concern with a certain level of severity.

##### Biographies

If you are writing related to fulfilling PCI compliance there should be a bio about the personnel involved whilst performing the assessment. You will specifically state that the consultant in question is qualified to perform the assessment accordingly. This gives the client peace of mind that the representative is qualified for the task at hand.

#### Dynamic

These may or may not need to be included in a report.

##### Exploitations and Payloads

This is an accounting for all of the actions performed by the penetration tester so that the forensics team can thoroughly search for remaining artifacts and remove them. This allows the team to differentiate a penetration tester from an active attacker within their network. All details for each payload implemented should be clearly defined so the client can effectively remove them all. 

##### Compromised Credentials

List all of the accounts with compromised credentials, or if an entire subset of accounts are compromised you could say 'all domain accounts' or similar. 

##### Configuration Changes

If you made any configurational changes to the client's environment, create an itemized list of all changes made so the client can revert them to a previous state or modify them to an improved state based on your assessments and recommendations. Restoring these settings yourself is preferred but may not be possible in all circumstances. Getting approval from a client before changing anything is standard to prevent angry clients or unintended consequences.

#### Affected Scope

A list of affected host devices might be too extensive to include here, so you can place them in another appendix to be referenced for this information. This may be displayed in a table with multiple columns in order to keep your report clean and concise. A bulleted list is not a good method for presenting this information as it could be multiple pages long and difficult to read through.

##### Information Gathering

When an external penetration test has been performed, there is a lot of information that was discovered externally via search engines. This section is intended to help the client understand their external footprint and what information is publicly available. This might mean whois data, domain ownership, subdomains, emails, accounts, public data breaches, SSL/TLS configurations, and even a list of open ports and services. Only include this if there is an obvious value to the client and avoid including frivolous information of low impact.

##### Domain Password Analysis

If you gain Domain Admin access and uncover the NTDS database, you should attempt to crack these passwords within reasonable standards. After completing this step, a tool like DPAT can be used to generate a report with statistics related to these passwords and their crackability. Include the key statistics from this report like the total number of obtained hashes, percentage of hashes cracked, number of privileged accounts cracked, top passwords, and number of passwords cracked per character length requirements. This section illustrates the value of strong password creation policies.

### Other Reports 

This writeup is mainly in regard to penetration tests specifically. While most reports will be similar, they will definitely be different and omit some sections while including some others that have not been mentioned.

It is advisable to use reports you have created to generate some templates for later use. This creates a sense of consistency which leads to easier production of reports in the future.

### Resources:

- [HackTheBox Home Page](https://academy.hackthebox.com/ 'the home page for hack the box')
- [HTB 1535 Notetaking and Organization](https://academy.hackthebox.com/module/162/section/1535 'the page for this hack the box module 1535')
