# Troubleshooting Windows 3.1

### Common Windows Issues

#### BSOD

*Blue Screen of Death* ( #BSOD) is a #Windows #stop-error that often occurs on #startup and shutdown due to bad #hardware, #drivers, or #applications.

##### Safe Mode

Starting the system in *Safe Mode* and trying to **use the Last Known Good, System Restore, or Rollback Driver tools to restore your system** to a previous image that still functioned properly.

##### BIOS Diagnostics

*Reseating or removing* #hardware would be your next course of action if you are not able to repair via operating system #software or #BIOS. Within BIOS you should find *hardware diagnostics tools* from the manufacturer that can help you solve this issue.

#### Sluggish Performance

When experiencing *Sluggish Performance* there are several things you can check for that may be negatively affecting your system:

##### Windows Update

Using *Windows Update* to install the current version of the #OS and update #drivers is easy and important. 

The *Task Manager* will allow you to check for temperatures and utilization of your hardware to see what is being overtaxed.

##### Limited Disk Space

*Disk Space* may be unavailable so try **eliminating unnecessary data and defragmenting** your disk if applicable.

##### Power Saving Mode

*Power-Saving Mode* may be engaged due to high temperatures and throttling of the #CPU.

##### Anti-Malware

Actively running #Anti-Virus and Anti-Malware may be running and slowing your system, or it could be that the #malware itself is causing issues.

#### Boot Errors

*Boot Errors* happen when the device is unable to retrieve data about the operating system upon startup.  **“Operating System not found”** and **“Missing operating system”** are common messages you will see when the bootloader has changed or there are multiple operating systems available on the *bootable media.*  Check for any flash drives or other #storage devices that may have #boot media on them. The **booting order may have also been changed** via your system #BIOS or #UEFI.

##### Startup Repair

#Startup *repair* can be used to try to **diagnose and solve the issue of a missing operating system** or other #boot failures.  You can also modify the *Windows Boot Configuration Database* ( #BCD) formerly known as *boot.ini.*  This is **in the recovery console as: bootrec /rebuildbcd**

#### Common Error Messages

Missing #NTLDR originated with **Windows NT and indicates that the Windows boot loader is missing.**  Run *Startup Repair* or manually replace the #boot media and reboot the system.

*Missing Operating System* occurs when **Boot Configuration Data is incorrect** – this can be remedied by running *Startup Repair* or manually configuring the #BCD store.

*Booting to Safe Mode* means the operating system is not starting normally – **running Startup Repair should remedy this issue.**

*Device Not Starting* is usually due to a bad driver, **check Device Manager and Event Viewer to diagnose and remove** or replace the appropriate driver.

##### Services

*One or More Services Failed to Start* means you are experiencing **issues with your drivers or hardware.**

*Try starting the service manually.* Check the account #permissions to see if it is being blocked. Confirm any dependencies the service may have via the #Services option and see if they are working correctly. If it’s a problem with a Windows service, check system files.  If it is a problem with Application services, reinstall the application in question.

When #Applications stop working you may see an error message with an explanation, but sometimes the application will just stop and disappear. 

Your *Computer is Low on Memory* indicates that you **do not have sufficient** #RAM to run a given application.  Running multiple applications at the same time requires more RAM.

Checking the *Task Manager* for memory-consuming #processes is an easy way to see what the culprits are and free up additional RAM. 

*Increasing Virtual Memory* is an option on the Windows #OS found in **System > About > Advanced System Settings > Performance > Settings > Virtual Memory.**  This will allocate parts of your storage drive to temporarily work as additional, #virtualized #RAM.

#USB *Controller Resources Exceeded* is an issue that occurs **related to the ‘endpoints’ of the USB devices.**  Each device has a different set number of endpoints – **if you exceed a total number of endpoints then you have run out of available resources and additional controllers will not work.**  It is difficult to know the number of #endpoints a device has.

A solution to this problem is **switching all USB 2.0 devices to 2.0 ports,** and following suit with the 3.0 ports and devices. The 2.0 system may support more endpoints and free up resources (endpoints) for other parts of the system.

*Windows System Instability* is due to **errors with software, system hangs, and application failure. **

Perform diagnostics via the *Windows Memory Diagnostics Tool.*

#### Reliability Monitor

Check *Reliability Monitor* to view a history of the problems associated with the application.  Sometimes resolutions are offered within this interface. Using what you have learned from Reliability Monitor, you can check the *Event Log* for additional reconnaissance for diagnosing the issue.  If you cannot resolve the issue in this manner, simply reinstall the application and try again.

***NEED TO CHECK OUT THESE THINGS AND FAMILIARIZE MYSELF WITH THEM AND SETUP MY OWN COMPUYTER AND CHECK OUT FIREWALL AND RELIABILITY MONITOR AND EVENT VIEWER*** 

Do diagnostics on the hardware including **hardware manufacturer diagnostics and storage and memory checks. **

#### System File Checker

Run *System File Checker* ( #SFC) and perform an anti-malware and #anti-virus scan.

*Slow Profile Load* refers to **roaming user profiles on domain-based authentication systems having slow access to the #authorization process and data access.**  These profiles are able to be used on any device in the network, but sometimes there is #network #latency accessing the #domain controller which slows login #scripts transfers, application of policies and #permissions, and may require hundreds of #LDAP queries.

Sometimes a client will try to connect to a remote #domain controller instead of the local devices which is due to problems with your local #network infrastructure.

*Time Drift* is a natural occurrence with computers, over time the **clock will eventually get out of sync** no matter what you do.  Since this is a problem with the technology itself, we need to address the symptoms of the clock as time goes on. 

Enabling *Automatic Time Settings* via **Settings > Time & Language > Date & Time** to set *automatic timekeeping,* which will sync with a clock server and periodically correct your system clock.  If you have privacy settings enabled, you may see the wrong time zone – this can be corrected manually in the configuration settings.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/troubleshooting-windows-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [013 Task Manager](013%20Task%20Manager.md)
- [014 Windows Control Panel](014%20Windows%20Control%20Panel.md)
- [023 Malware](023%20Malware.md)
- [023 Anti-Malware Tools](023%20Anti-Malware%20Tools.md)
- [031 Troubleshooting Solutions](031%20Troubleshooting%20Solutions.md)
- [033 Removing Malware](033%20Removing%20Malware.md)
- [534 The BIOS](534%20The%20BIOS.md)
- [634 BIOS Settings](634%20BIOS%20Settings.md)


#study #professormesser #comptia #Aplus #taskmanager #reliabilitymonitor 