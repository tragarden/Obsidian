# Examining Group Policy

Group Policy is a #Windows features used to configure rights and privileges for local settings. If an attacker were to gain control of Group Policy Objects, then they can move laterally throughout the organization seeking to escalate privileges.

A Group Policy Object ( #GPO) is a virtualized policy applied to individual users and devices. GPOs manage timeouts, USB ports, domain password policies, software installs, remote access settings, and application management. One GPO may be associated with multiple containers, and each container can have multiple GPOs. 

### Order of Precedence

| Policy Level | Description                                             |
| ------------ | ------------------------------------------------------- |
| Local Group  | The most broadly applied policies                       |
| Site         | Applies to the Enterprise Site the host resides within. |
| Domain-Wide  | Applies across the given domain.                        |
| OU           | Applies to users and devices within the given OU.       |
| Nested OU    | Yields specific permissions to OUs nested in other OUs.                                                        |


#### Group Policy Management Console

The Group Policy Management Console is an Administrative Tool for the Windows system and can be accessed via command line. When this domain is created, the Default Domain Controller policy is the defaulted GPO for the domain. This has higher precedence than any other GPO. 

The GPOs are processed in an order of how granular the details of their policies are. If you are considering a nested #OU, this would be processed last because the rules of more broadly applied policies will be rendered before the OU. The OU would take precedence over Domain-level policies because the more specific rules of the OU may override the rules of the domain level policies, since it is processed last.

The precedence of the GPOs follows a Link Order that indicates when that GPO will be processed. The lowest Link Order is processed last.

Toggling #Enforced will force the settings of a specific GPO. This is used by applying this rule to a higher level domain, which will then override the lower-level domain and OU policies. This used to be referred to as 'No Override' in older variants of Active Domain.

Block Inheritance is specified for an OU, preventing higher level policies from being applied to the OU.

#### Refresh Rate

GPO settings are not immediately applied as Windows will only update the group policies on 90 minute intervals. Domain Controllers update their group policies every 5 minutes. It may take up to two hours for a policy to go into effect. Update intervals can be modified in the Group Policy settings. The update process can be initiated with the following command:

- gpupdate /force

