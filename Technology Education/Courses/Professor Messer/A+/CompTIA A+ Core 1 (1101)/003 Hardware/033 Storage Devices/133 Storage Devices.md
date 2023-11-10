# Storage Devices 3.3

### Hard Disk Drives

*Hard Disk Drives* ( #HDD) are a form of **non-volatile magnetic storage that uses mechanical parts and fast spinning disks** to store data indefinitely.  These devices are **random access, meaning that you can retrieve data from any location within the drive**.  This is different than magnetic tape-based memory, which must be rewound to the physical point the data is stored on.  The **mechanical components in this drive limit the speed** of the device, take up space, and can also break over time and use. 

The fundamental design of these devices incorporate a **platter that mounts to a spindle that spins the platter**.  Adjacent to this mechanism is an **arm that reads the information on the platter, and an actuator that controls the arm’s position** over the disk.  At the end of the arm is a **head that reads the data** off the disk.  There are multiple layers of platters, each with their own arm and head as well. 

*Rotational speed* ( #RPM) is directly related to **average rotational latency** – the faster you spin the platter; the faster data can be transmitted to and from the drive. 
### Solid State Drives

*Solid State Drives* ( #SSD) is another form of non-volatile #memory that is more modern than the HDD style drives.  SSDs are **very fast drives that DO NOT use mechanical parts** and use #serial communication via #SATA to communicate quickly to the host.

### M.2 NVMe Drives

*Non-Volatile Memory Express* ( #NVMe) is the next technological step for drives, as they had **lower latency and could operate at SSD speeds via the M.2 interface** on newer motherboards.

M.2 is the **smallest form factor** yet, which **doesn’t need SATA or power cables via the PCI Express bus** connections.  **If using the NVMe PCIe x4** bus, these devices can operate at **speeds exceeding 4GB/s**.

It should be noted that M.2 uses **different connector types, known as a B key or an M key**.  Some devices are compatible with both B key and M key form factors.  Check your motherboard documentation to find out if you have an M key or B key setup. 

M.2 does not necessarily guarantee that you are using NVMe – **M.2 devices can still operate on the AHCI standard**.  M.2 drives slide into a designated slot and are then fastened to the motherboard via a screw.

### Flash Memory

#Flash Drives use *Electrically Erasable Programmable Read-Only Memory* ( #EEPROM) which is also known as flash memory.  It is a form of **non-volatile memory** and does not need a power source to retain data.  These devices have a ***finite number of writes and are NOT suitable for archiving data*** as they can be easily damaged or lost.

#USB *Flash Drives*, *Compact Flash* ( #CF), *Secure Digital* ( #SD), #miniSD, #microSD, and #xD-Picture Cards are all forms of flash EEPROM memory drives.

*Optical Drives* **read small bumps on physical media with a laser beam**, known as **microscopic #binary storage**.  It is a slow form of media used for archiving data that will not often or ever need to be changed.  Formats for physical media include **CD ROM, DVD ROM, and Blu-Ray**, and drives include internal and external solutions.
### Form Factors and Connectors

*Mini-SATA* ( #mSATA) came with the advent of SSDs and allows for a **smaller form factor** that can fit into laptops and mobile devices.  Since there is **no spinning drive or mechanical parts**, they can be much smaller, which brought on the need for smaller SATA connectors as well.  These were only used for a brief period before being **replaced by M.2 form factor** drives. 

*Advanced Host Controller Interface* ( #AHCI) is **used by SATA to transfer drive data to the systems RAM at speeds up to 600 MB/s** – SSDs made this interface obsolete as they required higher operating speeds.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/storage-devices-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [053 Troubleshooting Storage Devices](053%20Troubleshooting%20Storage%20Devices.md)
- [134 Motherboard Form Factors](134%20Motherboard%20Form%20Factors.md)
- [233 RAID](233%20RAID.md)
- [234 Motherboard Expansion Slots](234%20Motherboard%20Expansion%20Slots.md)
- [334 Motherboard Connectors](334%20Motherboard%20Connectors.md)
- [434 Motherboard Compatibility](434%20Motherboard%20Compatibility.md)
- [431 Peripheral Cables](431%20Peripheral%20Cables.md)
- [631 SATA Device Cables](631%20SATA%20Device%20Cables.md)
- [831 PATA Device Cables](831%20PATA%20Device%20Cables.md)
- [931 Adapters and Converters](931%20Adapters%20and%20Converters.md)

#study #professormesser #comptia #Aplus #M2 #nonvolatile #opticaldrive #optical