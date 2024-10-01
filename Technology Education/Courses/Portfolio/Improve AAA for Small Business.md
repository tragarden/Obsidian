### Overview

Assess the access controls, processes, issues, and provide appropriate recommendations for a small business. Evaluate the security controls used to manage access, authorization, and accountability of data for this group in order to decrease the likelihood of security risks.

### Scenario

You are a new security professional at a small business that does not currently have a security team. You will investigate a deposit made towards the business from an unknown bank account. Review the access log and access controls to determine if this action was performed by a threat actor before recommending mitigation methods to reduce recurring incidents.

### Project 

Information about who caused this threat:

- Event occurred at 8:29:57AM on 10/03/2023
- A user in the Legal/Administrator group used device Up2-NoGud at IP 152.207.255.255
- Event ID 1227 added payroll event FAUX_BANK

Issues:

- The account of Robert Taylor Jr. at \rt.jr\@erems.net performed this attack based on IP.
- This is a contractor account for the organizations attorney - they should not have access to finances and their account access should be audited.

Recommendations:

- An access audit should be performed to ensure principle of least privilege is enforced as well as separation of duties. The legal advisors should not have access to financial accounts.
- Access privileges should be removed from contractor accounts when they are not actively working within or for the organization. This can reduce future occurrences of unauthorized access and suggested inactivity time before account suspension should be 30 days.
- Using Multi-Factor Authentication is recommended to limit access to authorized users only.