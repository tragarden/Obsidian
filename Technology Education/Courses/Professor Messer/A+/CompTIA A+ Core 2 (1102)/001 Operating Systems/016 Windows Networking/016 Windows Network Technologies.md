# Windows Network Technologies 1.6

### Shared Resources

A *shared resource* is a **folder or printer that is available to other devices on the #network,** which can be viewed in *File Explorer.*

When a resource is assigned to be #shared, it must be **mapped to a drive letter so it can access file servers and automatically connect.**  **Shares should be visible to anyone on the network,** although the #sysadmin can place a ‘$’ at the end of a share name to remove it from search results.  Via *Administrative Tools* or *Computer Management* windows, we can modify these shares and see the complete list.

#Mapping a drive **associates a drive letter to a specific available share,** which is then visible within ‘This PC’.

To share a #printer, we can **use File Explorer, Settings, or Printer Properties to create a share** from an existing device.  You can also #blacklist / #whitelist users from using the device within this interface.  Troubleshooting can be accessed from the *Printer Properties* as well.

When adding a shared printer to the list of local devices, the **list of available new devices should automatically generate a list containing the printer** you are seeking.  In the event that it is not automatically found, you can select a shared printer by name in the format //serverName/printerName, where the ‘//’ denotes a server instead of a file or folder.

### Proxy

A #Proxy is used to **divert or reallocate incoming internet traffic along a different path** or to a different destination.  This can be managed within **Settings > Network and Internet** or by the alternative route **Control Panel > Internet Options > LAN Settings.**  A proxy may not work in every situation.  In the settings you can enable or disable the automatic proxy detection feature or choose to do it manually.

### Network Locations

*Network Locations* are used to assess #security concerns based on your location.  **While in your home location, you will use ‘Private’ location settings** as you will likely have full access to your home network and all related devices without any security concerns. **Public location will be prompted when you are accessing a new or public #Wi-Fi hub** – this will limit your connectivity to other devices and prevent certain forms of access requests to your device.

### Network Paths

*Network Paths* let us **manage our active connections to different shared devices.** Here you can also **map the drive letter to your share** as well as other management features such as the option to disconnect from a share.

#### Metered Connections

#Metered Connections is used to **set limits for the amount of data our computer can receive** from the internet or local network.  From the metered connection window, we can **set the data limit, reset dates and durations, set app permissions for data use, and see a list of our apps and how much data they are using** and when.  This is a ***useful tool for slow networks, limited bandwidth, and usage-based billing.***

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/windows-network-technologies-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [011 An Overview of Windows](011%20An%20Overview%20of%20Windows.md)
- [011 Windows Features](011%20Windows%20Features.md)
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [018 Operating Systems Overview](018%20Operating%20Systems%20Overview.md)
- [021 Active Directory](021%20Active%20Directory.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [057 Troubleshooting Networks](057%20Troubleshooting%20Networks.md)
- [128 Network Tools](128%20Network%20Tools.md)

#study #professormesser #comptia #Aplus #software #microsoft #Windows 