# Managing Backups 4.3

### Backups

#### Procedure

When backing up a system there are many metrics to consider including:
1. Total space required
2. Backup methods
3. Media type
4. Location for #storage
5. #Software for backup and #recovery
6. Schedule for the backups

### Types of Backups
#### Full

*Full Backups* are all encompassing and **include all operating system and user files.**  This is the most time consuming and space intensive method of backup.

#### Differential

*Differential backup*s are **derived from an initial Full backup.**  After the initial Full backup, any future updates will only backup data that has changed since the initial. 

#### Incremental

*Incremental backups* also **derive from Full backups** and are similar to differential backups with an added step. This method **will only back up the changes to the previous incremental backup.** So, **when an item is modified, it becomes part of the incremental backup.** The next incremental backup will only include the changes performed to the previous incremental backup. **Restoration of a system like this is more intense,** as you will need the full backup and all incremental backups to retrieve all of your data. ***Great explanation of this at the 4:00 mark on the video for this lesson.***

#### Synthetic

*Synthetic backups* use a Full backup and incremental backups.  After a set duration, the **incremental backups and the original full backup are combined into the new synthetic backup.**  This eliminates the high storage needs of Full backups and the intensive restoration time needed for incremental backups.

#### On-Site

*On-Site Backups* are often the **cheapest storage options and do not require an internet connection and give immediate access** to data.

#### Off-Site

*Off-Site Backups* **require an internet connection** or #WAN link allowing restoration and data #recovery to be performed from anywhere at almost any time. Your **data should be more secure** via this method.

***Often organizations use both on-site and off-site backups and #storage*** for their own respective advantages.

#### Grandfather-Father-Son

*Grandfather-Father-Son Backups* refer to **three backup rotations used in unison** – a trio of **monthly, weekly, and daily scheduled backups.**  The twelve monthly backups are the grandfathers, the four or five weekly backups are the fathers, and the daily backups are the sons.

#### 3-2-1

*3-2-1 Backups* are common for both business and home use.  This means having **3 copies of data at all times – one primary copy and two backups on different devices.**  These backups should be on at least 2 different types of media. ***One copy of the media should be off-site, via physical displacement or #cloud backup.***

#### Disaster Recovery Testing

*Disaster Recovery Testing* **simulates a catastrophic failure of the system and is used to assess how much data can be recovered** if this happens. This is a common audit that may be done weekly, monthly, or quarterly, and verifies that if disaster happens, there will be some peace of mind about how much data can be recovered successfully.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/managing-backups-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [053 Troubleshooting Storage Devices](053%20Troubleshooting%20Storage%20Devices.md)
- [133 Storage Devices](133%20Storage%20Devices.md)
- [233 RAID](233%20RAID.md)

#study #professormesser #comptia #Aplus #hardware 