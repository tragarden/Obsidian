# Best Security Practices 2.6

### Basic Methods

#### Full-Disk Encryption

The best thing you can do to secure your systems and #network is to use full-disk #encryption including any data-at-rest.  You will **encrypt all drives and all file systems for the best outcome.**

#### Backups

Making backups is critical and making sure you know #encryption keys matters greatly. Sometimes these are stored in the *Active Directory,* but most of the time you should secure your own #backup anyway.

#### Password Entropy

*Password Entropy* is a concept where if you use **more complicated phrases or sequences in your password, this makes it increasingly difficult to crack** as an attacker.  Using a mix of cases, words, symbols, and special characters is the most effective way to create good password entropy.

It is good practice to **make sure that all passwords expire,** usually in terms of 15, 30, 60, or 90 days.  A critical system may perform password expiry every 15 days. The #recovery process for a user should be complex enough to ensure that the user is not an imposter.

***ALWAYS change default passwords and usernames*** – it is important to note that the #BIOS and #UEFI **have logins that need to have their passwords changed,** otherwise someone that knows the default system passwords will have control over your BIOS/UEFI.

Implementing a password for screensaver mode on your systems is a good way to increase #security.  This is useful because it can automatically lock the device when it is unattended, so no stranger can walk up and use it while the User is called away.

#### Physical Tethers and Lockers

Laptops can be easily stolen, so use a locking system to physically secure their #hardware to a locking tether.

#### Screen Filters

*Personally Identifying Information* ( #PII) **include names, addresses, SSNs, birth dates,** etc. and need to be protected from *shoulder surfing* via *privacy filters* for your screen and facing your screen away from windows and passerby. 

### Account Management

#### Permissions

*Account management* means setting user #permissions, **assigning group rights, and setting login time restrictions.** Login time restrictions can be set so that devices cannot be accessed after working hours, limiting access to third parties.

#### Old Accounts

It is good practice to **disable unnecessary or unused accounts** including many default accounts that come with any operating system.  Disabling the guest account for a system is usually a first target.  Definitely change all default accounts from the stock username and password.

#### Interactive Login

*Disabling interactive logins* is useful as not all accounts will need to log in.

In #Windows there is a #Policy called **Interactive Logon Machine Account Lockout Threshold**  which lets you **set the amount of password attempts permitted** at login. 

The Policy called Interactive Logon Machine Inactivity Limit **defines the idle time required before the system goes to screensaver and locks the active user out.**

### AutoRun and AutoPlay

#AutoRun and #AutoPlay are features from versions of ***Windows prior to 7.***  This **was a feature that would automatically execute files from inserted media which became a major security threat.** AutoRun can be disabled via the registry, or via autorun.inf in ***Windows Vista.***  Settings  > Bluetooth and Devices > AutoPlay will allow you to disable autoplay on your device.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/security-best-practices-comptia-a-220-1102-2-6/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [024 Social Engineering](024%20Social%20Engineering.md)
- [044 Safety Procedures](044%20Safety%20Procedures.md)

#study #professormesser #comptia #Aplus #security #socialengineering #activedirectory 