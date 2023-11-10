# Troubleshooting 3.1

### Common Solutions

#### Rebooting

**Rebooting the system is the easiest way to begin troubleshooting, because it will reset all the #applications, #hardware, #drivers, #services,** and more which can sometimes correct issues that have happened from the system running for too long.  

A #bug in the #router #software could be **inhibiting your #network traffic** and a #reboot might clear the corrupted data. 

Sometimes #applications use too many resources, and a quick look at the *Task Manager* can illustrate which applications are overtaxing the system.

#Memory *leaks* slowly increase #RAM consumption until there is nothing left.  Rebooting clears the RAM and alleviates the memory leak.

##### Rebooting Services and Applications

*Restarting Services* can be useful as well.  #Services are **background applications without user interfaces** or interaction.  It is similar to the normal computer #processes we manage, and can also **cause memory leaks, crashes, and resource consumption.** Check *Task Manager Services tab* to manage Services via right click.

When #Applications aren’t working correctly, their files and configurations can be managed within Settings > Apps > Apps & Features where you can repair, reset, or uninstall apps. There are additional options within the *Control Panel,* under the *Programs and Features* option.  Running the application setup again is another option for fixing applications.

#### Repair and Reset

The *Repair* option **for apps will install missing files, replace corrupted files, fix application shortcuts, repair the registry entries, and reconfigure and update relevant drivers.**

The *Reset* option will **perform a factory reset** on the app, removing all user data and installing the original files again.

The *Uninstall* option will **remove the application and all related data** from the device.

#### Minimum Requirements

*Verifying Requirements* is something that has to be considered when installing applications and operating systems – if you do not have the appropriate #hardware to support the data within the application, it will not run.  You need to check #CPU speed, total #RAM, #video capabilities, device #drivers, and runtime libraries. Use *System Information* to determine your current hardware configuration and capacities.

If you do not meet system requirements, check *Resource Utilization* via *Task Manager,* and compare your existing capacity for resources to what the manufacturer suggests for its application.

Installing new #hardware if you do not meet the minimum requirements is often the only option.

If you are lacking Disk space, check the *Disk Cleanup* option provided by #Windows to free space.

#### System File Checker

*System File Checker* ( #SFC) will **verify the source and integrity of every system file** to see if they have been modified or corrupted over time.

#### Startup Repair

*Startup Repair* can be accessed via **Settings > System > Recovery,** or from the *Advance Boot Options menu* and will give you the option to *Repair Windows.* Windows should give you the option to *Troubleshoot,* and this is where the *Advanced Options* menu is available. This will diagnose the settings within #Windows and change them to make things work again.

### System Reimaging

#Reimaging or Reloading an #OS is a form of **system recovery where a prebuilt image is used** to instantly put a set of applications and configurations onto a computer that is experiencing issues.  This is time saving as it avoids the process of searching for OS problems, which can be time consuming especially compared to how easily and fast reimaging can be done.

#### Windows Restore

*System Restore* or *Windows Restore* can be found in **System > About > System Protection under System Restore.**  Here you are able to choose a point in the history of the device to revert to, which should hopefully **restore the system to a previously known-to-be-good version of the OS** that works. Choose a point you would like to restore to, and the system will return to that point in time without modifying your data.

Reset via Windows 10: Settings > Update & Security > #Recovery

Reset via Windows 11: Settings > System > Recovery

#### Windows Update

*Windows Update* centralizes all OS and driver updates and can be configured to only run at specific times, meter connections, and download directly from the publisher.

#### Update History

*Update History* is part of *Windows Update* and will allow you to view the changes to your system over time. This can be found within **Settings > Update & Security > Windows Update in Windows 10 or within Settings > Windows Update** for Windows 11.

#### Windows Profiles

*Rebuilding Windows Profiles* will need to be done when profiles become corrupted, yielding error messages like **‘The User Profile Service failed at logon” or “User Profile cannot be loaded”.** Sometimes related documents are missing, and the account must be deleted and recreated.

Deleting a profile requires logging in to the computer with #Domain **Administrator rights and renaming the \Users\name folder,** which will save some important files.

Backup the user #registry by right clicking #HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList and selecting ‘Export’. Once you have saved this registry data, deleted it, and renamed the users folder, restart the computer.

Restructuring a profile requires logging into the user account allowing Windows to rebuild the account and recreate the \Users\name folder.  Then you will login as the #Domain #Administrator again to copy over the #registry and important files.  DO NOT copy the entire profile over as it may contain corrupted files!

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/troubleshooting-solutions-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [013 Task Manager](013%20Task%20Manager.md)
- [014 Windows Control Panel](014%20Windows%20Control%20Panel.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [021 Active Directory](021%20Active%20Directory.md)
- [025 Windows Security Settings](025%20Windows%20Security%20Settings.md)

#study #professormesser #comptia #Aplus #taskmanager 