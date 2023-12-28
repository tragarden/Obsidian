# Hack the Box Modules

Hack The Box began as a training ground for IT specialists who wanted to practice their cyber-security skills on Virtual Machines with known vulnerabilities. The original iteration of Hack The Box used 'black box' style VMs that provided no help, clues, hints, or guidance. 

Hack The Box Academy was bourn from a necessity to educate individuals interested in cyber-security that didn't have an existing relevant educational background. HTB Academy introduced newcomers to vital concepts like Information Security, Network Administration, Active Domain, Databases, Software Development, Linux, Windows, Command Line, and Internet Protocols. 

### Testing Flow Patterns

It is often hard to conceptualize the process for penetration testing, but there is a logical order and means of organization presented by HTB Academy. The following steps are presented in a general order to organize the path forward when pentesting.

1. Pre-Engagement
2. Information Gathering
	1. Vulnerability Assessment
		1. Exploitation
		2. Post-Exploitation
		3. Lateral Movement
3. Proof of Concept
4. Post-Engagement

#### Pre-Engagement

Pre-Engagement refers to the period before we actively begin our testing procedures. This is when an agreement is forged between the client and pentester in the form of a contract. The contract defines the goals of the test and related information such as scope of the work, limitations and permissions, and tests that will be performed.

#### Information Gathering

Once we have agreed and committed to the terms of our contract, we can begin collecting data during the reconnaissance phase of our work. We will identify the systems we are observing and any information that is openly available about these systems.

It is very important to take detailed and organized notes about the discoveries we make and to save this data in a way that is easily reviewed. Even if you find an obvious vulnerability during the early stages of discovery, it is wise to continue gathering information until you have exhausted the resources available to you.

We will discover the current version state of the systems we are penetrating, operating systems, software in use, hardware, network data, IP addresses, subnet and LAN information, enumerating vulnerabilities with tools like #nmap, and any other facet of information that is gathered during our introductory view of the systems. 

#### Vulnerability Assessment

Once we have gathered data during our discovery phase, we can begin to review our notes and findings and determine viable methods for exploitation. We can scan the systems with our set of tools to determine the best vectors of attack as well as patterns of failure the client is falling into. 

During this phase we will evaluate possible vulnerabilities using automated scanning methods as well as looking through our notes and discovered data. We may find flaws in applications, software, user credentials, firewalls, Active Domain, and other aspects of the system we are evaluating.

If we are able to identify known vulnerabilities we can then begin to exploit them in an attempt to gain access where we should not be able to. There are multiple paths forward from this point that are to be performed in no particular order. This is a time for recognizing patterns and weaknesses in the target system.

#### Exploitation

Exploitation can happen after we have performed enumeration and detected some vulnerabilities. Exploitation would indicate that we are not yet able to access the system and will need to exploit a vulnerability we have uncovered. 

Once we gain access, it is natural to assume we can progress to the next phases: the Post-Exploitation phase or Lateral Movement phase. However before we can commit to this, we must gather more information now that we have new privileges within the system. This is especially true if we do not uncover any points of access or vulnerabilities worth exploiting - we can return to the information gathering phase to attempt to discover other options.

Exploitation can occur in many ways - we can try brute-forcing passwords, exploiting network and web application services, flaws in network design, and Active Directory inconsistencies. 

##### Web Exploitation

Web Applications are varied and one organization may use dozens of web applications. This expands the attack surface and typically offers many new vectors for attack through third parties and inconsistencies in configurations. The range of protocols, languages, and points of communication create a wide range of vulnerabilities that are useful when pentesting.

Web Applications mean that databases and websites are involved, allowing us new methods of attack such as #SQL and Command Line ( #CLI) injections, as well as database exploitations.

#### Post-Exploitation

While we may have gained access during our Exploitation phase, it is unlikely that we were able to obtain Administrator or Superuser privileges. This means that we need to further gather information until we find adequate means of privilege escalation. The ultimate goal of privilege escalation is to gain control of the ***Domain Administrator*** role in the **Active Directory** environment. Having access to the Domain Administrator role will give us access to all user accounts within the organization. 

When we (once again) gather information during the Post-Exploitation phase - this is known as #Pillaging. This is a very vital stage of information gathering because we should be able to access more information about other users, software, and network structure than at any other point in our process so far.

After Pillaging, we can once again assess our newfound vulnerabilities from our new set of privileges. You may go back and forth a few times between pillaging and exploitation as you continuously uncover new privileges laterally and through escalation.

If we obtain control over all levels of user accounts, we may move on directly to the Proof-of-Concept stage.

##### Lateral Movement

Lateral Movement refers to the post-exploitation phase of accessing user accounts that have the same level of privilege as user accounts we have already successfully exploited.  During this phase we can explore all the newly controlled user accounts and continue gathering data throughout these newly accessed accounts.

#### Proof of Concept

Proof of Concept ( #POC) is documentation proving to a System Administrator that you have detected vulnerabilities and were able to gain unauthorized access to aspects of the system. This will show a clear path of exploitation that the sysadmin will be able to perform themselves so they can remediate this problem and prevent further attacks. Remediating the flaws of a whole system can be costly in time and resources, so this duty is left to the organizations team to correct. 

#### Post-Engagement

The Post-Engagement phase is when we eliminate all traces of our work in the target system. This means undoing the damage we caused during our tests and restoring the network we infiltrated back to the state we found it in. Leaving shells open or ignoring a new account we created could cause problems for the organization moving forward. All of our actions will be recorded and neatly presented to the organization as we complete our tests and return the system to the organizations default state.