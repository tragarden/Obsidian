### Overview

I am responding to an incident with a malicious file hash that I have previously investigated via VirusTotal. Now I will respond to the incident's alert ticket by following a playbook related to phishing attacks.

### Scenario

I am an L1 in a Security Operations Center ( SOC ) for a financial service company that had malware installed on an employee workstation after a malicious executable file was installed from a phishing email. I previously verified that the email was malicious by investigating the files SHA256 hash in VirusTotal. Now I will be following the playbook provided by my organization to resolve the alert by observing security policies and procedures. A flowchart is provided for completing the investigation, resolving the alert, and closing the ticket.

### Project 

##### Step 1

I have received the ticket in regard to the phishing attack. 

##### Step 2

I have reviewed the alert associated with the ticket and changed the ticket status to "Investigating".

##### Step 3.0

I have reviewed the email and observed that it does have an attachment and related hash value.

##### Step 3.1

I have converted the file to a SHA256 hash value and reviewed this value in the VirusTotal website, confirming that this file is indeed malicious and installed malware capable of Windows system manipulation. 

The sender email address appears to be an incomprehensible string of random characters related to a strange IP address. The email address has no relation or similarity with the sender's name 'Clyde West'. 

The subject line has typos and misspellings are consistent throughout the body of the email. This indicates that the sender is likely not a serious applicant for an engineering position.

##### Step 3.2

After reviewing the content of the email and confirming that the attachment contains malicious content, I have chosen to escalate the ticket to L2 members of the SOC. This decision was based on spelling and grammar inconsistencies within the email, a suspicious email address and IP, and the analysis of the attached file which proved to contain malware via VirusTotal online tool. I have thus escalated the ticket as directed by the playbook and related flowchart.


