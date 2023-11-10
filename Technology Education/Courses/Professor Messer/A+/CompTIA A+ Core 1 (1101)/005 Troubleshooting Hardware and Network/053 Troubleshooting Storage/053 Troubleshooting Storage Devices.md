# Troubleshooting Storage 5.3

### Disk Failure

*“Cannot read from the source disk”* indicates a **read/write failure of the designated drive**.  This is the most ominous symptom of a failed drive.  **Sometimes the drive merely has slow performance**, if this is occurring you will probably note that there is some sort of #LED on the device to *indicate that the drive is constantly re-trying to access data or write* to the disk.  If you hear a loud clicking sound, this is the click of death and indicates a damaged drive that may need replacement or repair.

If you experience disk failure, you should **try to back up the drive** if that is at all possible. After backup, further **inspect the device for loose or frayed cables**.  Ensure that your system is **not overheating after startup** and **check to see if the power supply is providing adequate power**. Sometimes after new devices are added to the machine, this can change the needed power output from the power supply. Perform #HDD diagnostics from the manufacturer on a machine that you know is operating normally.

### Boot Failure

#Boot failure is indicated by the *error message* **“Drive not recognized” or “Boot Device Not Found”** accompanied by blinking lights and possible beeping.  **“Operating System Not Found” indicates that you do not have a readable #OS file** on the drive the computer is booting from. 

For boot issues, check the drives to **ensure good physical connections** of all cables.  After checking the hardware, **check the boot sequence** in the #BIOS settings.  Sometimes a #USB drive is **accidentally selected as the intended boot drive**. If the problem persists, check the configuration of the device, and attempt a reinstall if that doesn’t work.  You can **try different #SATA slots** as well to see if maybe a slot on the #motherboard is damaged or otherwise inoperable.  If you think the drive has failed, try it on a normally functioning computer before disposing of the drive.

***The first rule for Data Loss / Drive Corruption is PREVENTION.  BACK UP YOUR DRIVES IN ADVANCE: HDDS WILL EVENTUALLY FAIL!!!***

**All HDDs will fail** as they are mechanical and have moving parts.  **Repairs to these drives are difficult and costly**, must be performed in a dust-free environment, and may not even be successful. Occasionally an #SSD will no longer be able to write but can still read files.

### RAID Failure

The **“RAID not found” error indicates a RAID controller that is failing** or missing.  Check your #RAID management software to diagnose and identify the drive that is either missing or failing.  You MUST check the RAID console before you start modifying hardware in any way.

>RAID 0 requires 2 or more drives – any failure will break the array system.

>RAID 1 requires 2 or more drives – failure of one drive will not break the array.

>RAID 5 requires 3 or more drives – this accommodates the failure of a single drive.

>RAID 10 requires 4 or more drives – you can lose all drives except for one from each set of mirrors.

*Self-Monitoring Analysis Reporting Technology* ( #SMART) is a system that **uses RAID utilities to automate the monitoring of your RAID array**.   SMART will avoid hardware failure by taking preemptive measures like **scheduled disk scans** and notifying you of the warning signs of drive failure.  You can see detailed information such as **spin-up times, error count, start and stop counts, cycle count, and total hours of On time**. 

### Drive Speeds

*Input/Output Operations Per Second* ( #IOPS) is a performance metric that **measures how fast we can read and write data** to and from a drive.  For reference, an **HDD can operate at about 200 IOPS**, where an ***SSD is capable of 1,000,000 IOPS*** thoroughly crushing the performance of an HDD. What happens during this process is initial memory access, communication across a serial bus, spinning up the drive and accessing data, then reading and writing data to and from the drive. 

### Missing Drives

If you notice that some drives are not showing within your OS file browser, but everything boots normally, check out the #BIOS settings and the connections of your internal drives.  If your external drives aren’t being detected, there may be a bad cable or lack of power to the drive.

### Network Shares

*Network Shares* are connected during startup via login script and can then be used as shared drives.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/troubleshooting-storage-devices-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [051 How to Troubleshoot](051%20How%20to%20Troubleshoot.md)
- [052 Troubleshooting Common Hardware Problems](052%20Troubleshooting%20Common%20Hardware%20Problems.md)
- [133 Storage Devices](133%20Storage%20Devices.md)
- [233 RAID](233%20RAID.md)

#study #professormesser #comptia #Aplus #hardware 