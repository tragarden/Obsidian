# Troubleshooting Hardware 5.2

### POST

The *Power-On Self-Test* ( #POST) is a **test of system components that runs before your operating system boots** up.  This test will **check for main #hardware, #video signal, and #memory** availability.  If any of these fail to function properly, you will hear beeps or see codes displayed on the screen depending on what variant of #BIOS you have.  These beeps are proprietary and different for each manufacturer.

#### Issues with POST

Common issues found during POST include **blank displays, incorrect BIOS time and setting, or attempting to boot from the wrong device**.  If you have a **blank display**, that could be due to bad video signal, bad #RAM, bad #CPU, or a misconfiguration of BIOS.  If the **time is incorrect**, you may need to replace the battery on the motherboard that keeps track of this information.  If you are **booting to the wrong device**, then you need to change the boot order in BIOS or put #OS files on the drive the computer is reading from. 

#### BSOD

A **Windows Stop Error** is also known as the ****Blue Screen of Death**** ( #BSOD) or the frowny face for #windows 10.  This is a screen that users dread seeing.  It will contain information that may be useful for troubleshooting, or you can also check the **Windows Event Log** for more details.  Once you have collected information, you can contact the manufacturer of the computer, they will have more troubleshooting information since they are familiar with the hardware you are using – #Microsoft is not helpful in this aspect. 

You can alternatively go to https://www.windows.com/stopcode and enter the #stopcode provided on the *Stop Error page*. 

In the case that you get no #video after Windows boots, **toggle #VGA mode via the (F8) key**.

If your computer is able to enter #safemode, this **can yield clues as to what is failing since there are certain drivers that run during this time**.  If you can enter safemode, these drivers are working successfully.

BSOD can occur for a variety of reasons, **bad hardware, bad drivers, and bad applications** being the primary culprits.  If you are consistently experiencing BSOD, **go back to a different system bookmark, such as ‘Last Known Good’, System Restore, or Rollback Driver**.  If this is still not working, **remove or reseat all cables and hardware**.  **Run hardware diagnostics** provided by the manufacturer or BIOS.

### Mac OS X

*Mac OS X* uses a *Spinning Wait Cursor*, and its BSOD counterpart is known as the ***Spinning Ball of Death*** ( #SBOD).  This is feedback indicating that something is happening, but sometimes it will get stuck.  This could be due to a #Mac **application freezing, bad #hardware, or bad paging to the disk**.  Restarting your computer is a common way to address the SBOD.

*Black screens* on the monitor have some simple solutions.  First, you will **check to see if it is plugged in**; might seem redundant but this is the most common solution to this issue.  You can additionally check to **make sure the power and signal cables are mated properly** to the socket.  **Check the inputs** of your monitor as well as the ***brightness controls***, someone could have bumped these buttons and rendered their screen dark.  If none of these solutions are viable, try using another #display to determine if it’s the monitor or the computer. 

### Power Issues

If your computer is receiving no power, **check the power source via multimeter or handheld #AC tester**.  **Check for any illuminated LEDs or fan operation**.  Sometimes the fans will spin but there is no power to the other components.  Maybe the fans are spinning because they operate with lower voltages than the other components. **Check where your fan power is coming from**.  If your computer will not enter #POST, you may have a bad #motherboard.

*Slow performance* can be caused by a few sources.  *Task manager* is a good place to start, you can **check for high #processor usage and input/output of different hardware** components. **Limited disk space, anti-virus applications, Windows Update, and power-saving mode are all common culprits** causing sluggish performance. 

### Overheating

#Overheating is another common problem and is **almost always a physical issue**.  **Dust and dirt will collect on  your components, building up and cooking onto the surfaces** over time as they generate a lot of heat.  Remedies to overheating include **heat sinks, cleaning, more fans, and increased airflow**.  You can check the operating conditions and temperature of your hardware via software provided by the #BIOS or HWMonitor from [http://www.cpuid.com/](http://www.cpuid.com/)

***If you smell smoke or something burning, disconnect the power immediately***.  Wait until the system has had time to cool and then examine the motherboard for points of failure.  These may be repaired, but you may have to replace the motherboard in many cases. 

Excessive **heat can cause intermittent shutdowns**, and when this happens Windows will usually record details about this in the *Event Viewer*.  This may happen if you are playing a particularly taxing game, otherwise it is likely your fans, heatsinks, and positioning of the computer itself.  **Windows will shut the system down to protect components if things get too hot**.   Failing hardware can be another cause of overheating.

### Application Issues

*Application crashes* are usually accompanied by an *error message*, but sometimes the #application will just close with no indication as to why.  Checking the *Event Log* and *Reliability Monitor* are useful tools for diagnosing issues with applications.  The **reliability monitor will show a history of the problems** this application has had before, as well as suggesting possible resolutions if available. If these are not solutions, reinstall the application and then contact the manufacturer support if that does not work.

### Noises

*Noises* are a consideration when diagnosing computer issues.  Y**ou should only hear a light hum emitting from the computer, any other noises are suspect** and should be investigated when you first hear them. ***Rattling is from loose components, scraping is often a hard drive sound, clicking indicates fan issues, and a pop might mean one of your capacitors has blown***. 

### Freezing

*Lockups* refer to when the **computer freezes completely, often without writing to the Event Log**.  You should check for any activity such as lights or a response from Ctrl-Alt-Del.  **Updating drivers and software may alleviate this problem** without much additional issue.  If that’s not the issue, **use hardware diagnostics to determine if your #RAM or #storage capacity are inadequate**.

*Continuous reboots* are an annoying issue that can be ***mitigated by pressing (F8) to boot from the last working configuration via Safe Mode***.  While you are in *Safe Mode*, you can also **disable automatic restarts in the System Properties tab**.  If these don’t work, inspect your hardware to determine if any of it has failed and is causing a reboot loop. 

### Incorrect Time

*Inaccurate system time* is caused by the **failure of a battery on the #motherboard**. Until this is replaced, you will need to reconfigure the #BIOS every time that you boot the computer on older units.  On modern computers, the #battery will not affect the BIOS configuration, and if you wish to reset this you will need to use a jumper to reset the flash memory of the device.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/troubleshooting-common-hardware-problems-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [CPUID](http://www.cpuid.com/)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [031 Troubleshooting Solutions](031%20Troubleshooting%20Solutions.md)
- [043 Managing Backups](043%20Managing%20Backups.md)
- [051 How to Troubleshoot](051%20How%20to%20Troubleshoot.md)
- [052 Troubleshooting Common Hardware Problems](052%20Troubleshooting%20Common%20Hardware%20Problems.md)
- [110 macOS Overview](110%20macOS%20Overview.md)
- [135 Computer Power](135%20Computer%20Power.md)
- [534 The BIOS](534%20The%20BIOS.md)

#study #professormesser #comptia #Aplus #systemrestore #rollback #taskmanager #windowsupdate #eventviewer #eventlog #reliabilitymonitor #hardware 