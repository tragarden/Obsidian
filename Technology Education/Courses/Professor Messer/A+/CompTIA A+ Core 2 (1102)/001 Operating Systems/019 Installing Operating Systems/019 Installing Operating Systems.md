# Installing Operating Systems 1.9

### Installation

To install an #OS, you will need to **create bootable media containing the install data** for the operating system.  This is **usually done via flash drive,** but installing an #HDD or #SSD, or ROM based optical media with the install data is sufficient as well.  When you start your system with the drive inserted, you will need to tell the #BIOS which drive you would like to #boot from, select the drive with your bootable media, and restart your system. This should prompt you to install the media on the device, granting you access to the OS. 

#### Booting

*Preboot eXecution Environment* ( #PXE “Pixie”) allows you to **perform a remote OS installation** over your #network. 

Alternative boot methods include **network downloads,** where your device can connect to the internet and **retrieve the OS files via the system BIOS.**  “Hot swappable” or **external drives can be used to mount #ISO images to a device.**  You can also create a #partition within the drive you currently use and **install bootable media to the partitioned area,** letting you have two operating systems on the same device.

#### Installation Types

There are several styles of installation, each addressing specific needs. 

*Clean Install* wipes your entire drive and **reinstalls a fresh iteration** of your chosen OS.

*In-place Upgrade* will yield a **new OS while maintaining all existing data** for your file system.

*Recovery Partition* is a **hidden partition that saves your previous OS install configuration** in case something goes wrong during the installation.

*Image Deployment* is a way to **install clones of an OS, files, and apps, and can be automated** to install on many devices simultaneously.  This means you can put the exact same OS and apps on thousands of units. 

*Repair Installations* **fix problems with #Windows** without altering user files. 

*Remote Network Installations* **use a local server or shared drive to install an OS** across your network.

#### Special Cases

In special cases you may experience inoperable #hardware because drivers are needed – sometimes your OS #BIOS will be able to acquire these #drivers and install them so the OS can successfully be installed.

### Partitioning

*Partitioning* a drive or disk partitioning is a way to **logically divide its total storage capacity into segregated sections.**  This can contain data that needs to be separated, and can facilitate multiple operating systems. In #Microsoft’s nomenclature, a formatted partition is known as a #Volume.

#### Partition Standards and Tools

*Globally Unique Identifier* ( #GUID) *Partition Table* ( #GPT) is the **newest standard for partitioning allowing for 128 partitions of up to 256TB** on windows or 9BillionTB otherwise.  **GPT requires a #UEFI BIOS.**

*Master Boot Record* ( #MBR) is an older standard that is limited in a few ways, with **max partition sizes of 2TB.**  **Your Primary partition is your Active one where you will** #boot from.  This format style **allows for only 4 partitions** total.  MBR extended contains additional logical partitions.

*Quick Format* **creates a new file table, but does NOT erase your data.**

Using ‘ #diskpart’ we can achieve a **Full Format which will write all zeros to your disk** – a full reset of the data with no chance of recovery.  This will also perform the time-consuming process of checking the disk for bad sectors.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/installing-operating-systems-comptia-a-220-1102-1-9/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [018 Operating Systems Overview](018%20Operating%20Systems%20Overview.md)
- [053 Troubleshooting Storage Devices](053%20Troubleshooting%20Storage%20Devices.md)
- [133 Storage Devices](133%20Storage%20Devices.md)

#study #professormesser #comptia #Aplus #software 