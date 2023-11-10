# Active Directory 2.1

### Active Directory

An *Active Directory* is a #database of **all computers, accounts, shared files, printers, groups,** and more within a #network.  This is where #authentication **credentials can be managed, passwords reset, and accounts deleted.**  Think of it as #centralized access control for the entire network.

#### Windows Domain

A *Windows Domain* is a **name associated with a related group of users, computers, resources,** or others. This information is **stored within** *Domain Controllers* which are **managed by the** *Active Directory.*

*Organizational Units*  ( #OU) are a **method of organization for databases** where a #sysadmin creates their own hierarchy of management.  OU’s can be made for any group you would like to create – they can be very large or small.  They usually describe an attribute of the members within the group.

#### Login Scripts

*Login Scripts* are used to #automate tasks upon login which can be applied to specific users, groups, or organizational units.  You can associate these #scripts with a group by going to **User Configuration > Policies > Windows Settings > Scripts.**

Normally these scripts will be set for each workstation, and not applied to an entire group of users.

#### Group Policies

*Group Policies* **manage groups of computers or users** under *Local and Domain policies* via the *Group Policy Management Editor.*  This is a console where login scripts, network configurations ( #QoS), and security parameters are configured.  You may update this client with the #gpupdate utility via > gpupdate /force.

#### Home Folder

The *Home Folder* can be a #network folder, meaning that you will have **access to it from several devices** as long as they are within the local network.  This will **save the files to the network instead of the device.** You will need to do minimal training to educate users on using this folder.

#### Folder Redirection

You can use *Folder Redirection* to send Desktop, Downloads, Music, Downloads, etc. folders **to the network share folder.**  Redirection can be assigned in **User Configuration > Policies > Windows Settings > Folder Redirection.**  This is used in conjunction with *Offline Files,* where they will be uploaded once you reestablish a connection to the network.

*****TRY THIS IRL AND PLEASE NOTE HOW TO DO THE REDIRECTION PROCESS YOURSELF*****

#### Security Groups

#Security Groups make it easy to **assign permissions to different groups of people with different levels of authority.**  A user can simply be added to a designated group to attain their given rights.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/active-directory-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)

#study #professormesser #comptia #Aplus #activedirectory #grouppolicy #windowsdomain #Microsoft #Windows #security 