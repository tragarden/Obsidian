# Data Destruction 2.8

### Managing Data Hardware

We use *physical destruction methods* when we are certain that **data must be absolutely destroyed and is the point of no return for data.**  Common methods include **drilling through disks, hammers, degaussing via electromagnets, and incineration.**  The electromagnet removes the magnetic field from the drive and renders the electronics inoperable, destroying the drive.

Third party companies often perform drive destruction for an organization by supplying a paper-trail of the broken data along with certificates for each destroyed device.

**Low-level formatting is part of OEM manufacturing** and is not for the end user.

*Quick format* installs a #boot #partition, file system, and clears the master file table (but not the data). This means that **there are methods for recovering the data after formatting.**

*Regular format* **overwrites every sector of your drive with zeros,** fully erasing all information from the drive.

*File Level Overwriting* **only erases data from the filesystem,** and you can recover this data with the right software.  This can be done with #Sdelete on #Windows.

*Secure Data Removal* can be done with third party apps like *Darik’s Boot and Nuke* ( #DBAN) which removes all data on the drive and resets everything back to zeros.

*Physical drive destruction* is the only sure way to make sure data cannot be recovered from your drive.

In 2019 the company Blancco and Ontrack purchased 159 used storage drives from eBay and found that 66 of these drives still had data and 25 of them had sensitive PII data from the previous user.  Included in their findings were an email archive for a travel agency, shipping details for a freight company, and college student documents.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/data-destruction-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)

#study #professormesser #comptia #Aplus #hardware 