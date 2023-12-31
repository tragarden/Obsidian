# Post-Engagement

 Post-Engagement focuses on restoring the system we have worked on to its previous state and reporting all of our documentation for our process to the client. 
### Cleanup

During our testing we will install tools, upload scripts, add accounts, disable or delete things, and change configuration settings. This whole process must be well documented because during the cleanup phase - we will restores all of the changes we have made to the system to their original values the organization used. Using our own documentation we can review our process and undo it in a methodical way.

### Reporting

It is crucial to document every step in our process in order to prepare a detailed report for our client and to be able to clean up after we are finished. This means documenting screen recordings, command entry, screenshots, hosts we interacted with, configuration changes - any interactions we had should be documented!

Our report should include at least the following items:

- Attack Chain - what methods did we take to compromise the network, in what order, and what time.
- A laymen-friendly summary.
- Remediation method suggestions with references to outside sources.
- Risk-rating explaining the level of concern for the vulnerabilities observed.
- Means of reproducing the exploitations, proof-of-concept.
- A detailed list of every interaction we had in the system.
- Short-term and Long-term suggestions for remediation.

#### Report Meeting

After we have drafted our report there will be a meeting with the client to explain the various points of the report and to offer clarity where it is lacking. This will offer space for the client to ask questions so they can fully understand not only what we have done to their system but what they can do about it moving forward. There are few boundaries to what information we present, but a solid example would be terms of remediation. A pentester would suggest a solution such as 'sanitizing user input', but this tester would NOT supply code or techniques for doing so as this falls outside the scope of our work.

##### Deliverable Acceptance

When we initially submit our report it will be a Draft of the report which has not been finalized. We can only submit our final review after the client has reviewed the draft we have submitted. After their comments and suggestions are heard, we revise our draft to include all information the client needs for their auditing purposes. Auditors will often NOT accept a report in draft form.

#### Data Retention

After testing has concluded it is required that you maintain the data related to your client for a set amount of time. This allows the client to contact you post-test to request data from the testing process. This data must be held securely on company hardware with strong encryption, as there is likely a lot of the organizations sensitive data stored there. A Virtual Machine ( #VM) must also be created to simulate the organizations network in case they request solutions for their unique environment in the future.

#### Final Steps

After we have finished the testing we will need to provide an invoice for the client and collect payment. This is also the time that we supply an post-engagement satisfaction survey. This phase typically depends on customer service skills, communication, and memorable dialogue from an enthusiastic and socially competent tester. Having a strong relationship with the client is far more important than executing impressive testing measures.

[PCI-DSS Penetration Testing Guide](https://www.pcisecuritystandards.org/documents/Penetration_Testing_Guidance_March_2015.pdf "PCI-DSS penetration testing guide")