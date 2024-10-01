### Overview

Perform a risk assessment based on vulnerabilities that threaten organization operations and prioritize resources based on risk scores. This assessment is part of the NIST CSF and will help the security team determine their security posture.

### Scenario

You are working on the security team for a commercial bank that is conducting a risk assessment of current operations. This involves the creation of a risk register to focus efforts towards the most vulnerable risks.

A risk register is a centralized record of potential risks to assets, information systems, and data. Your supervisor requests that you evaluate a set of risks from the risk register. You will determine the likelihood of occurrence, severity level, and then calculate a risk score based on these criteria. You will then generate a priority queue for addressing these risks.

### Risk Assessment

##### Location

Based on the risk assessment provided by the security team we can state that while the bank exists in a region with low crime rates, theft is still possible.

The regional location of the bank is near coastline, which could result potential damages from flooding or storms.

##### Employees

There are 120 employees of the bank that each carry their own risk due to human error, social engineering attacks, and internal threats both intentional and unintentional.

There are 20 remote employees which create a heightened level of data in transit which poses an increased threat for interception by external threat actors. Technology kept outside of the physical offices of the bank pose additional threats for theft or environmental compromise. 

##### Customers

There are 2,000 individual customer accounts with the bank and 200 commercial accounts. All of theses accounts face regulatory penalties if the organization does not secure this data and abide by PCI DSS standards for protecting credit card information. The protection of Personally Identifying Information ( #PII) and financial records must remain secure, encrypted, integrity maintained, and confidential.

##### User Accounts

Between the employees and customers, there are approximately 2,320 accounts associated with the organizations regular operations. This does not include contractors and third parties.

##### Sponsorship

The reputational status of the bank as well as marketing from the local sports team and 10 local businesses must be considered as the bank adheres to regulatory standards and maintains good standing with customers and businesses in the region. 

##### Availability

The Federal Reserve maintains that the bank must have available cash for all possible transactions on any given day of operation. These funds must be available to customers in order to adhere to regulatory standards and remain compliant.

#### Assessment

| Asset | Risk | Description | Likelihood | Severity | Pritority |
| ---- | ---- | ---- | ---- | ---- | ---- |
| Funds | Business Email Compromise | Social Engineering Exploitations or Human Error | 2 | 2 | 4 |
| Funds | Compromised User Database | Poor Encryption Standards | 1 | 3 | 3 |
| Funds | Financial Records Leak | A database is publicly accessible | 3 | 3 | 9 |
| Funds | Theft | The safe is left unlocked | 1 | 3 | 3 |
| Funds | Supply Chain Distribution | Delayed delivery of cash due to natural disasters | 1 | 2 | 2 |

### Priority

In order of most severe to least severe:

- Financial Record Leak - 9
- Business Email Compromise - 4
- Compromised User Database - 3
- Theft - 3
- Supply Chain Distribution Interruption - 2