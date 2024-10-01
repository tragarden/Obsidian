# Writing Reports

Reports for Bug Bounty Programs should be orderly and concise. Smaller companies will require explanations in more laymen terms as they may not have developed security teams to interpret the report you are submitting.

Elements of Bug Bounty Reports include:

- Vulnerability Title
	- Vulnerability Type
	- Affected Domains
	- Affected Parameters
	- Affected Endpoints
	- Vulnerability Impact
- CWE and CVSS Scores
- Vulnerability Description
- Proof of Concept ( #POC) - methods of reproducing the vulnerability
- Impact
	- Business Impacts
	- Maximum Potential Damage
- Remediation Methods

### CWE 

Common Weaknesses Enumeration ( #CWE) is a list of weakness types in common language developed by the security community. CWEs provide baselines for identifying, mitigating, and preventing weaknesses.

### CVSS

Common Vulnerability Scoring System ( #CVSS) should be used to relay the severity of the vulnerability in a standardized way.

You can use the [CVSS Calculator](https://www.first.org/cvss/calculator/3.1 'a calculator for CVSS scores') to indicate the severity of the vulnerability you have found. The caluculator will intake the following parameters:

- Attack Vector Path - Network / Adjacent / Local / Physical
- Attack Complexity - Low / High
- Level of Privileges Required - None / Low / High
- User Interaction Requirements - None / Low
- Scope - Unchanged / Changed
- Confidentiality - None / Low / High
- Integrity - None / Low / High
- Availability - None / Low / High

[HackerOne](https://docs.hackerone.com/hackers/submitting-reports.html 'report guidelines from hackerone') has guidelines for how to write and submit a professional reports.

Some Examples include:

- [Remote Code Execution in Slack](https://hackerone.com/reports/783877 'report on slack vulnerability')
- [XSS on Google](https://hackerone.com/reports/691611 'report on XXS attack on google portal')
- [XSS on HackerOne](https://hackerone.com/reports/474656 'report example for hacker one XXS vulnerability')
