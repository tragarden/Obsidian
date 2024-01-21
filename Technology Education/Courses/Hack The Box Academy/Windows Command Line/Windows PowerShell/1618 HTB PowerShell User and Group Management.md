# User and Group Management

User accounts are a method of identifying and authenticating a user before granting them access to resources or a host device. They fall into one of four categories:

- Service
- Built-In
- Local
- Domain

### Built-in 

Built-in accounts are default user accounts that are present after an Operating System ( #OS) is installed. Every instance of #Windows will have the following accounts by default:

| Account       | Description |
| ------------- | ----------- |
| Administrator | performs administrator duties locally            |
| Default       | used by the system for multi-user authenticated apps            |
| Guest              | limited access for temporary users - best practice is to disable this account            |
| WDAG Utility              | let's Windows Defender Application Guard perform sandbox sessions            |
### Active Directory

Active Directory ( #AD) is the de facto application that Windows uses to manage authentication within an enterprise environment. This means AD is used to manage all users, hosts, network devices, file shares, group policies, and interactions with other organizations. 

In #PowerShell, we are able to manage users and groups in the Active Directory using the ActiveDirectory module for PowerShell.

### Local vs Domain Users

Local Users are the users defined on a single host. There is typically a limited amount of these users as in most cases a single computer will not have many users.

Domain-joined users are all the users on the network that fall within the constrictions of a specific domain. This could be thousand of unique users across a network of hundreds of hosts. This means a lot of accounts to manage and a lot of potential vulnerabilities for privilege escalation with these accounts.

### User Groups

User Groups logically organize user accounts to assign permissions to groups of people that need access to different resources at different levels of privilege. While this can be useful locally on a single host, it really becomes a powerful administrative tool when we apply it to a corporate domain or large network. We can create groups so that we do not have to individually assign rights to each user - simply add them to the relevant groups and they will inherit privileges from the parent group.

#### Get-Command \*user\*

We can use the Get-Command cmdlet in conjunction with the noun 'user' to discover all the commands associated with managing users with the following command:

>Get-Command \*user\*

#### Get-LocalUser

The Get-LocalUser cmdlet will list all users that have access on the given standalone host.

#### New-LocalUser

We can create a new user with the New-LocalUser cmdlet.  After creating this user a password will need to be created or else #Windows will identify this user as a #Microsoft Live account. In order to make this a local account, we will need to set a password with the Set_LocalUser cmdlet.

#### Set-LocalUser

We can configure a local user account with the Set-LocalUser cmdlet.

We can use the following commands to change the password for a newly created user 'JLawrence':

>$Password = Read-Host -AsSecureString
>Set-LocalUser -Name "JLawrence" - Password $Password -Description "CEO EagleFang"
>Get-LocalUser

#### Get-LocalGroup

Managing groups is very similar to managing users. The Get-LocalGroup cmdlet shows us all groups on the local machine.

#### Get-LocalGroupMember

If we want to see which accounts are within the 'Users' group, we can use the following command:

>Get-LocalGroupMember -Name "Users"

#### Add-LocalGroupMember

The Add-LocalGroupMember cmdlet allows us to add a user to a group.

We can use the following commands to add a user and then verify the user was added to the group:

>Add-LocalGroupMember -Group "Remote Desktop Users" -Member "JLawrence"
>Get-LocalGroupMember - Name "Remote Desktop Users"

### Managing Domain Users and Groups

In order to manage users and groups across our domain, we need to install both ActiveDirectory PowerShell module and Remote System Administration Tools ( #RSAT). If you have downloaded the AdminToolbox, you likely have these modules installed, however it is good practice to try to install them individually as the AdminToolbox module may be repackaged and may not have correct editions. 

We can install RSAY with the following command:

>Get-WindowsCapability -Name RSAT* -Online | Add-WindowsCapability -Online

This will install every feature of Remote System Administration Tools in the Microsoft Repository. 

You can install a lighter weight version of RSAT by downloading the package Rsat.ActiveDirectory.DS-LDS.Tools\~\~\~\~0.0.1.0

#### Get-Module

We can locate the Active Directory module with the following command:

>Get-Module -Name ActiveDirectory - ListAvailable

#### Get-ADUser

The Get-ADUser cmdlet can be used to find all Active Domain users or a specific one.

We can use the following command and the -Filter \* parameter to find all Active Domain users:

>Get-ADUser -Filter \*

If we want to find a user based on their Distinguished Name, #GUID, #objectSID, or #SAMAccountName - we simply use the -Identity parameter.

Use the following command to find an Active Domain user based on their Distinguished Name:

>Get-ADUser -Identity TSilver

The output from this command will reveal the following information about an AD user:

- Object class - is the object a computer, user, or other object?
- Distinguished Name - yields the relative path to the user's name in the Active Domain.
- Enabled - is this user active and logged in?
- SamAccountName - how the username is represented when logging into Active Domain.
- ObjectGUID - the unique identifier for the AD user.
- Other attributes beyond the scope of this module.

Furthermore we can use the Get-ADUser cmdlet with the -Filter parameter to search for attributes like associated email addresses.

We would use the following command to filter out all users that are NOT within the greenhorn.corp email address domain:

>Get-ADUser -Filter {EmailAddress -like '\*greenhorn.corp'}

#### New-ADUser

We can use the New-ADUser cmdlet to create a new Active Domain user account with a set of attributes and then validate that everything was implemented successfully. 

Using the following command, let's create a user account for Mori Tanaka, a new member:

>New-ADUser -Name "Mtanaka" -Surname "Tanaka" -GivenName "Mori" -Office "Security" -OtherAttributes \@{'title'="Sensei";'mail'="MTanaka\@greenhorn.corp"} -Accountpassword (Read-Host -AsSecureString "AccountPassword") -Enabled $true

#### Set-ADUser

If we need to modify the attributes of a Active Directory user, we can do so with the Set-ADUser cmdlet and then verify our changes as shown in the following commands:

>Set-ADUser -Identity MTanaka -Description " Sensei to Security Analyst's Rocky, Colt, And Tum-Tum"
>Get-ADUser -Identity MTanaka -Property Description

### Bloodhound

A noteworthy addition to this outline is the #Bloodhound tool for scanning the Active Directory. Misconfigurations of the Active Directory can be detected with this tool and conversely, an attacker can use it to discover means of privilege escalation.
### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy PowerShell Modules and Cmdlets](https://academy.hackthebox.com/module/167/section/1636 'HTB academy PowerShell modules and cmdlets guide')
- [BloodHound Active Directory Tool](https://github.com/BloodHoundAD/BloodHound 'link to the bloodhound active directory tool site)
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [1604 HTB Command Prompt and PowerShell](1604%20HTB%20Command%20Prompt%20and%20PowerShell.md)
