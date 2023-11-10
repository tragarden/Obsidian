# RAID Systems 3.3

### Redundancy

Data #Redundancy is important because it stores data on **multiple back up devices** in case one of them experiences failure of any kind.  ***RAID is NOT a way to backup these drives*** – it simply maintains active uptime and availability in the circumstance of device failure.

### RAID

*Redundant Array of Independent Disks* ( #RAID) is an array of inexpensive disks that **may or may not have redundancy**, despite the name. 

#### RAID Levels

RAID 0 is the #Striping level, named so because this level will **utilize two disk drives that both divide data evenly between the two drives**. This allows for **high speed and high performance** since the total work is managed by two drives yet carries ***additional risk because if you were to lose the data on one of the two drives BOTH sets of data would be rendered unusable***. This is an example of a system with ***ZERO redundancy***.

RAID 1 is the #Mirroring level of a RAID system and is a level with **high redundancy** as drive failure will not affect the availability of data. You may even **lose a drive without even realizing it**. Disk 0 and Disk 1 will contain the same data sets in the same order, meaning duplicate sets of data, which effectively **doubles the required disk space** needed. 

RAID 5 is known as *Striping with #Parity*, which is like RAID 0 where the file blocks are ‘striped’ to **distribute one set of data across at least 3 drives**. An additional set of data in the form of **Parity blocks will also be ‘striped’ into the dataset**, leading to **high redundancy** and data that is available ***even after drive failure***.  You may **lose some processing power and gain latency** through the calculations involved with parity.

RAID 10 (1+0) maintains the **high speeds of striping as well as the redundancy of mirroring** as long as at least 4 drives are provided.  This system combining striping and mirroring allows for the ***loss of up to 3 drives*** before losing any data.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/raid-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [133 Storage Devices](133%20Storage%20Devices.md)
- [053 Troubleshooting Storage Devices](053%20Troubleshooting%20Storage%20Devices.md)

#study #professormesser #comptia #Aplus #RAID0 #RAID1 #RAID5 #RAID10 #hardware