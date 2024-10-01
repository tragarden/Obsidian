### Overview

Consider the situation where you are walking through a parking lot and you discover a lone USB drive. You should consider the consequences that curiosity might yield if you were to plug this into a computer. Threat actors are known to leave USB drives with malicious content on them in an attack style referred to as USB baiting.

### Scenario

I am working for Rhetorical Hospital as a security analyst when I find a USB drive in the lot with the Hospital's logo printed on the case. I decide to use virtualization software to investigate this unknown USB device since I know that there may be malicious or compromising content on it. The simulation software is isolated and not connected to any other systems, devices, or networks which will prevent the device from spreading any malicious software if it exists.

### Project

Once I boot up the virtualized and isolated environment, I insert the unknown USB device and observe the contents. These contents belong to a user 'Jorge Bailey' who is the Human Resource manage for Rhetorical Hospital.

#### Contents

Contents of the USB drive for Jorge include:

Work related content:

- New Hire Template
- Shift Scheduling document
- Jorge Bailey Resume
- Staff Budget

Personal content:

- Vacation Ideas
- Wedding guest list

It seems that Jorge is using his device for both personal and work-related files, which is ironic because he should know that this is not appropriate for a work-purposed device. In addition to information about his personal friends information, there is personally identifiable information ( #PII) for employees and business costs within the contents of the drive. These sensitive work files are not secure which poses threats to regulatory compliance.

#### Attack Potential

The information on Jorge's drive poses security threats to employees at the hospital as well as his personal contacts. This information could be used to gather intelligence on hospital employees and personal contacts via social media research to threaten Jorge or exfiltrate sensitive information. This insecure drive could also leak information through Jorge's personal accounts and computers since he is clearly using the device for mixed purposes of personal and work-related activities which is a violation of CISA approved guidelines.

#### Risk Analysis

The fact that this device could have been obtained by a potential threat actor is the most obvious threat because it reveals sensitive information about the business finances and staff as well as Jorge's personal life. If this was an example of a USB baiting attack, this means that any one of the files could be an executable file containing malicious code masquerading as a benign file about a wedding, vacation, or staff data. This information could be used to infiltrate the business or use compromising information against the HR manager or other staff members, or even Jorge's personal acquaintances. This poses significant security threats to multiple parties and puts the business outside of regulatory compliance.

