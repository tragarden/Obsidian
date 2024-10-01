A Social Media company has experienced a data breach caused by undetected vulnerabilities. You will identify some network hardening methods and tools to increase security for the organization. The vulnerabilities must be identified and proper solutions must be suggested and you will explain why these solutions were chosen and how they can prevent further breaches in the future.

Consider solutions like port filtering, network access privileges, and encryption to offer solutions. Some of these solutions will be implemented one time, whereas others will be repeatedly performed as scheduled.

Customer personally identifiable information was leaked during this data breach, exposing names and addresses. The four main exposed vulnerabilities are:

- Employees Share passwords.
- Administrator password is set to default credentials.
- Firewalls do not have rules implemented.
- Multifactor Authentication is not used.

Select up to three hardening tools or methods to implement:

1. Password Policies
2. Multi-Factor Authentication for employees
3. Firewall configuration and maintenance

Reasons for these suggestions:

1. Password Policies will enforce unique password creation and ensure that they are regularly maintained. This will reduce the likelihood of successful brute force attacks and ensure that each employee account and resources like shares are secured. Enforcing a password submission limit is also recommended to thwart brute force attempts. Changing the default credentials for the administrator account and any others is mandatory for securing the network. 
	- This should be implemented one time.

3. Multi-factor Authentication will further increase the security beyond just improving password policies. This will ensure that the employee has more than one means of verification of identity. Suggestions for implementation include One-Time Passwords ( #OTP) or biometric input. A software application and OTP key generator could dramatically increase security when entering credentials and prevent all brute force attempts.
	- This method should be implemented one time.

5. Firewall Configuration will proactively protect the network from unusual network behavior. Blacklisting ports that are not needed for regular operations using port filtering options would be a worthwhile consideration. Creating rules or using a NGFW can be used to filter our unusual or suspicious traffic from brute force attempts and can offer additional protections to other threats such as DoS attacks. 
	- Firewall rules should be implemented once but monitoring should be regularly practiced and updating the firewall should happen weekly.