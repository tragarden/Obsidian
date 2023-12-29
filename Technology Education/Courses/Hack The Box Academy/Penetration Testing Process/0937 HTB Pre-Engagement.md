# Pre-Engagement 

Pre-engagement refers to the preparatory stage before we perform a penetration test. This is where the objectives and pentesting process are explained and discussed with a client. We try to present our testing methods and goals as clearly as possible to the client and come to an agreement that is executed in the form of a contract.

#### NDA

The signing of a Non-Disclosure Agreement ( #NDA) by all parties involved in the penetration testing is the first step in the pre-engagement stage.

- A Unilateral NDA is an agreement that one party will remain totally confidential while the other party is allowed to share information from the pentest with third parties.

- A Bilateral NDA requires both parties involved to remain confidential and prevents the sharing of any information related to the tests with third parties. This is the most common form of NDA a pentester will encounter.

- Multilateral NDAs is an agreement between more than two parties where all information must be kept confidential. This means that all individuals with knowledge of the tests completed must keep this information confidential. 

#### Stages

A Non-Disclosure Agreement must be offered before any discussion of pentesting can begin. This will always be the first step.

A Scoping Questionnaire will be offered to the client to determine their goals and desired methods for pentesting.

A pre-engagement meeting will be hosted in order to communicate with all parties involved in the test to answer any questions and address any concerns with the testing methods or objectives.

A Kick-Off meeting will happen on the day testing will begin in order to establish what will happen and to notify the appropriate authorities that network testing will be active and an outside user will be active within the organization.

#### Permissions

It is important to speak to the appropriate authorities within an organization to ensure that they are ordering this pentest in good faith. There have been historical accounts of estranged employees hiring a penetration tester to uncover vulnerabilities so this employee can attack their employer. You will want to MAKE SURE that you are permitted to test before you get into a complicated legal situation where you inadvertently facilitated an attack on a corporate network.

Individuals that are authorized to order a penetration test include:

- CEO
- CTO
- CISO
- CSO
- CRO
- CIO
- VP of Audits
- Audit Manager
- IT director
- IPSec Director
- Others 

### Documents

There are documents that are vital to protecting yourself legally that must be signed and seen by all parties involved in the testing. These documents include:

- Non-Disclosure Agreement
- Scoping Questionnaire
- Scoping Document
- Penetration Testing Proposal Contract / Scope of Work ( #SoW)
- Rules of Engagement ( #RoE)
- Contractors Agreement
- Post-Test Report

ALL OF THESE DOCUMENTS SHOULD BE REVIEWED BY A LAWYER BEFORE THEY ARE PRESENTED TO A CLIENT. 

#### Scoping Questionnaire

The Scoping Questionnaire is a way that we can quickly asses the needs and objectives of the client in terms they can usually understand. This will often be in the form of a checklist, some examples of categories are listed below:

- Testing for Internal Vulnerabilities
- Testing for External Vulnerabilities
- Internal Penetration Test
- External Penetration Test
- Testing Wireless Security
- Testing Application Security
- Testing Physical Security
- Testing Social Engineering
- Red Team Assessment
- Testing Web Application Security

After the initial checklist there will often be a more granular assessment to determine more detailed aspects of the network and intended testing. Some of the points evaluated will include:

- How many devices  to inspect within the network?
- The range of the #IP addressing and #CIDR.
- How many domains within the network?
- How many wireless devices are there and do we know the #SSID for them?
- How many web applications and how many roles are associated with them?
- Is a client list provided or is that part of our discovery during black box testing?
- Will there be a physical assessment that the tester will have to be present for?
- What are the goals of the Red Team?
- Will we assess Active Directory in addition to our other tests?
- Will this be a blackbox, whitebox, or graybox test?
- Will we be bypassing Network Access Control ( #NAC)?

#### Pre-Engagement Meeting

After signing the NDA we will have a pre-engagement meeting to discuss and explain the extent of our testing to the client. Information gathered during this meeting will help to inform our Penetration Testing Proposal Contract, or Scope of Work ( #SoW).

When creating the contract for our pentest, we can use the following checklist to ensure we have considered all facets of the testing:

- Non-Disclosure Agreement to ensure confidentiality.
- Goals List to determine our objectives.
- Scope that identifies the hardware, software, networks, domains, and accounts we are permitted to access and test upon.
- Pentest Type where we inform the client on what the tests do and discuss the advantages and disadvantages before the client chooses which test they would like performed.
- Methodologies discussed so the client understands what we will be doing while we are attacking their networks and the frameworks we use to do them.
- Locations - are the tests internal, external, remote, or all of the above?
- Time Estimation giving a general idea of when the tests will  begin and end.
- Third-Parties - identify all third parties so the client can contact them and notify them about the attacks that will occur on their applications or technologies. This is important for protecting yourself legally.
- Evasive Testing - are we surpassing the current security standards during our attacks?
- Risks - notify the client about risks and consequences involved with our testing. This helps to identify the limits of our tests per the clients requests.
- Limitations and Restrictions - what is off-limits - this is typically vital hardware that the organization needs to function properly.
- Information Handling - how will HIPAA, PCI, and other acts be enforced.
- Contact Information so we can keep in touch with all individuals related to our testing.
- Lines of Communication should be fully documented during all stages of the pentesting process. This means documenting email, telephone, and other communications.
- Reporting after the test is completed to explain our results to the client.
- Terms of Payment - who is paying and how much will it be?

The goal of this stage is to ensure we are working within the needs and wants of the client. We don't want to offer them something that they do not find to be useful. We want to design our tests to yield the best results related to their objectives.

#### Rules of Engagement

Our Rules of Engagement ( #RoE) can once again be explained via a convenient checklist. These rules define the limits of our tests and how we are permitted to access the network, accounts, domains, web applications, and any other facet of the organizations network.

- Introductory description of your document
- Name of the company and contractor job title
- Full company name, pentesters full name
- Contact info like email, phone number, etc. for all contractors and clients
- Purpose for the test
- Objectives of the client
- Scope of the client network
- Defined lines of communication i.e. email, phone, in-person, zoom
- Estimated times for starting and ending
- Times during the day where the tests occur
- Locations and type of connection 
- Methodologies such as OWASP 
- Objectives or targets for tests
- Using encryption and secure protocols when handling evidence
- Backups for restoration purposes
- Using encryption whenever possible
- Who do you report to when an incident happens and appropriate times
- Schedule for meetings and attendants
- Announce all retests if you haven't scheduled them
- Define your liability limitations 
- Disclaimers and waiving of damage or data loss
- Signature by an Authority to perform the test under this contract

#### Kick Off Meeting

The Kick-Off Meeting is usually in-person after all legal documents have been signed. This is where pentesters will describe a variety of attack methods like SQL Injection, DDOS, etc. to the clients. Tell them that if anything severe is detected, a report will be generated and sent to them during the appropriate working hours unless otherwise specified in the contract. Let them know the stresses the tests will place upon their network.

Taking this time to explain the testing process in a clear way that laymen can understand is a desirable skill at the kick off meeting. There will certainly be some folks that do not have a depthy knowledge of network technologies and will need it explained in a way they can understand.


Credit to Hack The Box Academy for these checklists. I try to rewrite my notes in my own words under a similar outline to what is presented by the author. 

#### Contractors Agreement

A Contractors Agreement is worth having if you are physically reporting to a work location. This will include similar data to the Rules of engagement, with information like building number, contact info, role, company name, reason for visit, etc. with a signed and notarized document proving your identity and reason for being there.
