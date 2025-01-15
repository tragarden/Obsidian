# macOS

macOS is the official term for the operating used on Apple computers. This is the second most popular operating system, following Microsoft Windows. It is most commonly used for home use, business management, graphic design, and artistic applications.

### History 

In 2000, Apple released the Kodiak variant of the original Mac OS X so that users could test it and provide user feedback. After receiving responses and making respective fixes, Apple released Mac OS X 10.0, named Cheetah in spring 2001. This was the first reveal of the new interface, named Aqua.

- OS X 10.1 was named Puma. This iteration improved system performance and began replacing OS X 9. 

- OS X 10.2, Jaguar, was released in Fall 2002. This iteration focused on interaction improvements and new applications like iChat.

- OS X 10.3, Panther, was released in Fall 2003. This was the first time Safari was available and replaced Internet Explorer as the default browser for Apple devices. Support for integrating with Active Directory was released at this time.

- OS X 10.4, Tiger, was the first to introduce widgets and dashboards. This was the first release of Apple products with Intel chipsets, replacing the PowerPC processors previously used.

- OS X 10.5, Leopard, was released in 2007 - one of the biggest years for Apple. The iPhone was revealed this year with iOS, which was based on Mac OS X. This iteration of the OS introduced Apple Time Machine along with support for 64-bit applications. This was also the first iteration of Mac devices that supported dual-booting via the Boot Camp app. This was the first time Windows OS could be used on Mac hardware.

- OS X 10.6, Snow Leopard, was released in 2009. The only changes were the addition of the AppStore and the discontinuation of support for PowerPC processors. At this point, Apple became based on Intel exclusively.

- OS X 10.7, Lion, was released in 2011. This brought successful features from iOS to Mac OS, such as gestures and saved window states. This also brought the introduction of iCloud to Mac OS X.

- OS X 10.8, Mountain Lion, released in 2012. This brought even more desirable features from iOS to the Mac OS X. 

- OS X 10.9, Mavericks, launched in 2013. At this point, Apple decided to adhere to a yearly release cycle for their OS. A change in nomenclature happened at this time - Apple departed from naming their OS iterations after wild cats and moved to locations and landmarks within California. Nothing substantial came with this release other than Apple stating that all future releasees would be free to upgrade.

- OS X 10.10, Yosemite, released in 2014. This revealed the addition of Handoff, which enabled users to move any task from one Apple device to another. The UI moved more towards the iOS look and feel. 

- OS X 10.11, El Capitan, brought performance changes and the ability to tile the screen with split views.

- In 2016 macOS officially replaces the OS X naming convention. With macOS 10.12, Sierra, Apple introduced integration for Siri, Apple Pay, and minor tweaks to the OS.

- macOS 10.13, High Sierra, released in 2017. This update made the switch to the Apple File System (APFS).

- macOS 10.14, Mojave, was released in 2018. This brought visual enhancements and the first iteration of Darkmode. Darkmode worked natively with all macOS apps and most third-party applications. Other iOS applications were brought over such as News, Stocks, and Home, among others.

- macOS 10.15, Catalina, released in 2019. This separated iTunes into multiple apps - Apple TV, Podcasts, and Music. This iteration further focused on bringing iOS features to macOS and allowed the use of an iPad as a second display via the Sidecar feature.

- macOS 11, Big Sur, released in 2020. This was the first version to move away from version 10 and brought notable changes to the UI and functionality of the OS. This iteration was the first to feature Apple Silicon processors while still supporting Intel processors for a period. Most of the focus of this iteration focused on bug fixes.

- macOS 12, Monterey, released in 2021. This brought integration improvements known as Universal Control. This brought ease to controlling multiple Apple devices at the same time. AirPlay underwent big changes, allowing the use of a Mac as a speaker when casting to other devices. Spatial Audio was introduced to FaceTime. SharePlay allowed you to share audio, video, and screen with other users via FaceTime.

- macOS 13, Ventura, released in 2022. This introduced a window management feature called Storage Manager. A facelift to the settings app, new Apps and app updates, and the Continuity Camera were released during this time as well.

- macOS 14, Sonoma, released in 2023. This iteration brought on Desktop Widgets, video conferencing on Safari, and optimized gaming.

- macOS 15, Sequoia, released on September 16, 2024. This featured the introduction of Apple Intelligence via the new Apple Silicon. Image Playground was a new feature that allowed for fun editing of images in Messages and Freeform, as well as third party apps. ChatGPT support from OpenAI was also available.

### Architecture 

Kernel: XNU

- The Mach kernel is the basis of the macOS and iOS XNU kernel architecture that handles the memory, processors, drivers, and low-level processes.

OS Base: Darwin

- Darwin is the base of macOS and is available for open-source use. Darwin was combined with other components like Aqua, Finder, and custom components to create the modern iteration of macOS. Darwin is a FreeBSD Derivative open-sourced by Apple.

#### Core Components

- GUI: Aqua is the basis for the GUI and visual themes for macOS. This provided additional support for other displays, rendering technologies, and more. It is known for it's flowy style, animations, and transparency of windows and taskbars.

- File Manager: Finder provides the Desktop experience and File Management functions. Aqua is responsible for the launching of applications.

- Application Sandbox: macOS and all apps use the concept of sandboxing to restrict the applications access outside of the resources needed to operate. This security feature limits the risk of vulnerability to the application itself so the macOS, files, and applications cannot be affected.

- Cocoa: the application management layer and API that macOS uses. It manages the behavior of applications within the operating system. It is also a development framework for bringing applications into the Apple ecosystem. Siri and notifications function because of Cocoa.

### GUI

The Apple GUI is powerful and one of the elements of macOS that draws users in. It is feature rich and understanding it is key to efficiency while working with Mac devices.

##### Components

- Apple Menu - point of reference for critical host operations like System Settings, screen lock, shut down, etc.

- Finder - provides the Desktop experience and File Management functions.

- Spotlight - serves as a helper that can search the filesystem and iCloud, as well as perform mathematical conversions and other tasks.

- Dock - located at the bottom of the screen by default, it acts as a repository for frequently used apps and currently open apps.

- Launchpad - an application menu where you can search for and launch applications.

- Control Center - manage network settings, sound and display options, notifications, and other items at a glance.

##### Root

You can view the root directory by launching the Finder app from the Dock, clicking on the 'Go' pane at the top, then selecting Computer > Storage.

Alternatively you can access the root directory is to launch Finder and then press Command + Shift + G and type '/', then hit Go.

##### Keymapping

Apple uses three function keys - Control, Option, and Command.

- Control on macOS = control on Windows.
- Option on macOS = Windows key
- Command on macOS = Alt on Windows

![[keyRemap.jpg]]

Copy and Paste is performed with Command + C and Command + V.

Duplicate a file by holding the Option key while you drag it to a new location.

Note that macOS does not allow you to 'Cut/Paste' files due to the possibility of data loss, although you can do this with text within an individual file.

Cutting and Pasting while using Finder is possible by using Command + Option + V to move a copied file.
1. Launch Finder.
2. Right-click on the file or folder you want to move and select Copy.
3. Use Finder to head to the location where you want to move the file

You could achieve this same process via terminal with the mv command - proceed with caution though because this is an irreversible command. 
1. Open Terminal from the Dock.
2. Run the following command to move the Test folder from the Users' Document directory to the Users' Desktop directory.

> mv /Users/tragis/Documents/Test /Users/tragis/Desktop/Test

#### Hidden Files and Folders

macOS hides many files and folders to prevent users from accidentally deleting critical files for the operating system. There are ways to view these files via GUI or CLI. 

Viewing hidden files via GUI:
1. Open the folder where you want to view hidden files.
2. Hold down Command + Shift + ' . '

Alternatively you could changes the default Finder view to include hidden files:
1. Open Terminal and run the following commands:

>defaults write com.apple.Finder AppleShowAllFiles true
>killall Finder

#### Preview Pane

The Preview Pane is part of Finder and allows us to see what files and images look like before they are opened. 

A preview of file contents is presented when you highlight with additional information about a file like Creation Date & Time, Last Modified Date & Time, Last Opened Date & Time, etc.

Enable Preview Pane within Finder and examine a file preview:
1. Launch Finder.
2. Click View at the top and select Show Preview.
3. Click any File and examine the contents.

#### Spotlight

Spotlight is the desktop search feature that will examine the entire macOS or iOS operating system. You can search for anything that exists on you device or iCloud.

### Movement

macOS has features like Mission Control and Split View to allow efficient workflow when using multiple apps. 

Mission Control is a feature that offers a bird's-eye view of all open windows, desktop spaces, and apps.

Split View is used to split your Mac screen between two apps. it automatically resizes the screen without manually moving or resizing windows. You must have two or more apps running in the background for this feature to work.

### System Hierarchy

The structure of macOS is based on standard Unix/Linux structure but creates it's own context for User, Local, and System directories. Many things you have learned about Linux will directly apply to macOS by default, sometimes using modified syntax. 

macOS divides the file system into multiple domains that separate files and resources based on intended use. 

Domains will apply access privilege to files and resources within a domain to prevent unauthorized users from modifying files.

The domains in the default system structure are below:

- Local Domain - contains resources like apps that are local to the computer and shared with all users.
- System Domain - contains system software from Apple
- User Domain - contains resources specific to each user that logs in. This displays the home directory of the user at runtime.
- Network Domain - contains apps and documents that are shared among users on the same local area network.

![[Mac File Hierarchy.png]]


### Standard Directories

The /Applications directory contains applications and their folders each belonging to a different domain, as depicted below:

- User Domain - applications installed and related to a particular user saved under /Users/username/Applications
- Local Domain - installed by a user or Apple that can be used by ALL users present on the computer are saved within /Applications.
- System Domain - applications related to the system or installed by Apple lie within /System/Applications

The /Users directory belongs to the User Domain and contains user applications, files, and resources. Each user account has it's own user directory. Each user can ONLY access their own /users directory and cannot access the directory of another user.

The /Library directory stores custom data files for applications, caches, configurations resources, preferences, and user data. The Local and System Domain Library directories are Global in scope while the User Library directory is specific to the user.

- User Domain - information about applications related to the current user are stored within /Users/username/Library
- Local Domain - information related to applications that are shared by all users are stored within /Library
- System Domain - information about system applications is stored in /System/Library

The Library directory contains the following key subdirectories:

- Library /Application Support - contains app specific support files, data files, and configuration files.
- Library /Caches - contains app specific support files that the app can re-create
- Library /Frameworks - stores libraries that are userd or needed to create an application.
- Library /Preferences - contains application preferences like PowerManagement, SoftwareUpdate, Logging, and more.

The /Network directory contains files that belong to the network domain. This contains a list of all computers in the local area network.

The /System directory contains system resources required for macOS to run. These are installed by Apple and should not be modified.

#### Unix Directories

Unix directories are similar to the default directories of Linux systems.

Here is a list of the default Unix directories:

- / - the root filesystem containing everything the os needs to complete a boot cycle. All volumes and filesystems are found here. This is like a buckett containing everything that the host needs, which is then stored in subdirectories like /etc, /home, and /usr.
- /bin - main storage point for binary files.
- /dev - maintains device ID files that enable the use of hardware devices on the system.
- /etc - contains system and application configuration files.
- /sbin - contains essential and common administrative binaries to keep the systems running.
- /tmp - stores temporary files for the operating system that do not need to be persistent. This directory is wiped clean on every reboot.
- /usr - contains libraries, applications like FTP, SSH, and vim. One of the largest directories.
- /var - stores system log files, sources for web servers, backups, and more.
- /private - stores critical system files and caches required for operation. They are hidden in the directory to ensure that they are not modified or deleted.
- /opt - stores third-party applications or packages that have been installed.
- /cores - contains Core Dumps stored by macOS intended for delopers for troubleshooting.
- /home - a subdirectory for storage of user Desktop, Downloads, and Documents folders.

To find out any information about the system hierarchy, use the 'man hier' command.

### Permissions

macOS permissions are directly based on Unix / Linux permissions. 

Every object on the host device belongs to a specific user or group. Every new item that is created belong to the user that initiated their creation, known as the User Owner. The primary group will always be the owner of the file. If preexisting permissions for group ownership are established, these will apply to the newly created files or directories.

Permissions are shown using base 8 or octal numbering. This is how we apply read, write, and execute attributes to the contents of User owner, Group owner, and Others within a file.

These octal representations are as follows:

- read (r) - octal value of 4
- write (w) - octal value of 2
- execute (x) - octal value of 1

Converting permission attributes' octal values can be difficult for people unfamiliar with the numbering system. We can use chmod-calculator to make these conversions.

We can use the following command to get Terminal output related to file permissions:

>ls -l

This will reveal the read, write, and execute permissions for the owner, users, groups, and others. It will also reveal the number of hard links, creator, file size, object type, and date of creation.

The default group for this os is 'staff' 

The acronym UGO is used to remember permissions in terminal User > Group > Other.

#### GUI Permission Management

When looking at a file, you can right-click it and select 'get info'. 
- Alternatively you could press Command + Option + I after selecting the file or folder.

This brings up a screen that displays the current permissions for the file, listed under 'Sharing and Permissions'.
- Click the lock in the bottom right corner and authenticate. This will enable you to make changes to the file.
- Select a User or Group from the name column and use the dropdown menu to modify the permissions.
- You  can also click the + and - buttons to add or remove users from the permissions list.
- Be conservative when granting permissions to important folders or files so that you do not expose sensitive data.

#### Terminal Permissions Management

When managing permissions via terminal, the chmod and chown commands are key to managing attributes related to permissions.

##### chmod

While in a directory in the Terminal, use the following command to display the files within the directory:

>ls -l

This will show the permissions related to the files within the directory.

Now let's issue the following command to change the permission attributes related to read, write, and execute. In this example we will be using the octal format 777:

>chmod -vv 777 HTB-Wallpaper-1.png

Now we can see the results of the change via the following command:

>ls -l

The permissionsn should have successfully changed from 644 to 777. The -vv switch is used to tell chmod to print out the old and new attributes in octal and symbolic notation.

##### chown

We can modify ownership of a file or directory using the chown command. Type the following command to change the owner of an indicated file:

>sudo chown htb-student HTB-wallpaper-1.png

Now we can observe the results with the following command:

>ls -l 

You should see that the file ownership changed from the previous owner to htb-student while the staff group retained access to the file as a group owner. We could also use chown command to change the group owner as well. We can see an example of this below:

>sudo chown htb-user:admins HTB-wallpaper-1.png

We can observe the changes:

>ls -l

Now htb-student should be the user-owner and admins should be the group owner. We could also use the chgrp command to specifically manage the group permissions.

### Networking

There are three ways to manage macOS  networking information: Terminal, System Settings, and Control Center. Using any of these features to manage network settings may require admin privileges.

#### Validating Network Hardware

We can check to ensure that our hardware devices are available and active for use. We can do this by checking the Network tab in the System Information application.
- Search for System Information in Spotlight or Raycast or launch it from the Launchpad.

This displays all hardware, software, and OS information. In the Network tab we can see active network interfaces.

#### Management via CLI

Note that Network Management via CLI in Terminal is not the preferred method for doing so. There are useful commands that can return information though.

If we type the ifconfig command into Terminal, we can see information related to our network interfaces and configurations.

>ifconfig

An example statement that could be used to configure Manual IP via ifconfig is below:

>ifconfig en0 inet \<192.168.1.1> netmask \<255.255.255.0>

This command will set the interface en0 to an IP address of 192.168.1.1 and the subnet mask 255.255.255.0.

It should be noted that  all changes made via ifconfig are temporary and will be overwritten by the networking service manager after reboot. In order to make changes persistent, you have to user NetworkManager in the GUI or through the networksetup command.

##### lsof

You will often need to check the status of port on your device. You can do so using the Isof command to see port states and what files have them bound.

>lsof -n -i4TCP -P

The string above displays all applications that are bound to TCP port / IPv4 Addresses but it does not present the port number's common name. If you want to see the protocol name, you can remove the -P switch.

This is a useful command because you can determine what user or context something is running in and what is communicating to and from our host.

#### Networksetup 

macOS comes with an application called networksetup that allows the user to check and configure networking preferences. This will require administrative privileges.

Here are some functional commands related to networksetup:

- networksetup -listallnetworkservices
	- this displays a list of all network services / devices on the hardware. This prints the logical name of the device.

- networksetup -listnetworkserviceorder
	- prints out the network services running and the order in which they are queried for connection. Services at the beginning of the list are checked first.

- networksetup -getinfo \<devicename>
	- gets info about a networkservice / device as the IP address assigned, subnet mask, gateway, and Mac-Address.

-  networksetup -getcurrentlocation
	- prints out the currently set network location

- networksetup -setmanual \<networkservice> \<ip> \<netmask> \<Gateway>
	- manually configures the IP address, network mask, and gateway for the specified device.

Note that there are MANY more commands for this application. They can be seen by simply typing 'networksetup' into Terminal.

>networksetup -help

#### Other

We can use the networkQuality command to determine information related to the interface's network quality:

>networkQuality -I \<interface>

This will display information related to uplink and downlink capacity, responsiveness related to ping and RPM, and idle latency.

We can use the security application to find the Password and SSID for the last connection you made. Security allows us to manage passwords, keychains, certificates, and more via CLI.

Print out a previous password with the following sample command:

>security find-generic-password -wa Office-2.4G

#### Tunnelblick

Tunnelblick is a free and open source method for controlling VPN connections on macOS. It uses OpenVPN config files and does not log traffic, IP addresses, or deliver ads. It allows for persistent VPN connections over device reboots - it will automatically reconnect to the last active VPN connection before a reboot.

#### Viscosity

Viscosity is a proprietary paid application that facilitates VPN usage on macOS. It is a one-time purchase of $14 that provides statistics related to your network use. It's a good solution for single-user, small business, and enterprise solutions.

#### Bonjour

Bonjour is Apple's open-source method of zero-configuration networking. It discovers devices and services on a network automatically via IP protocols, handling addressing, device naming, and service discovery. Printers, TVs, streaming devices, and other applications that allow media sharing can be detected by Bonjour.

This is useful from an administration perspective as it skips manual configuration for devices in a corporate environment.

From a security perspective, Bonjour can be complicated and cause security related issues.

mDNSResponder is a protocol used by macOS that performs the service discovery actions for the Bonjour suite. This means that any host capable of using mDNS can access hosts or other services that they may not have been granted access to.

#### Homebrew

Homebrew is a free and open-source package manager for macOS that is essential for developers and penetration testers. It allows for installation of many standard tools without having to manually compile open-source tools or downloading their dependencies.

Homebrew makes installing things like php much easier. Php was removed from default versions of macOS and without Homebrew, installing it would be time consuming and complicated as it requires manual compiling. Homebrew is so efficient at doing this that even PHP officially recommends using Homebrew to install it among other developer tools.

To install homebrew:

>-c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Once this command finishes, Homebrew has been installed and we confirm this with the next command:

>brew -v

This will return the version of Homebrew that is installed on your system. You may need to reboot terminal for this to display properly.

To install PHP, use the command:

>brew install php

This will install PHP and all requirements, which will allow the user to use php.

We can search for applications we have installed via Homebrew using the search command:

>brew search firefox

#### Cask

Homebrew Cask allows for the installation of GUI applications. 

To install Firefox and it's cask, use the following command utilizing the --cask flag:

>brew install firefox --cask

### Pentesting

Mac devices are popular among developers and security experts since they are versatile and secure. Most pentesting tools have versions that are compatible with macOS.

Virtual Machines are available for macOS via virtualization software like VMWare, Parallels, or VirtualBox. These applications need to be installed and then an ISO for the intended operating system must be selected and installed.

It is suggested that you use a VM for hosting pentesting work for two reasons: this means you will have a complete pentesting tool kit installed on the VM and it avoids causing damage to your real OS. This is a way of sandboxing potentially dangerous activities outside of your true operating system.

Some pentesting tools benefit from being installed directly onto macOS. This will give a significant increase in performance compared to operating them within the VM environment.

Tools that are commonly used for pentesting include:

- Nmap
- Burp Suite
- PowerShell
- Ghidra
- VSCode
- SQLMap
- VirtualBox

### Security

Executable files are the primary method for breaching macOS systems. Apple recommends the App Store and Identified Developers for any installation of applications. There is a setting that will limit downloads to meet these constraints - this is found within System Settings > Privacy and Security.

When you set the 'Allow apps downloaded from' feature to only include App Store downloads, you significantly increase the security of your device and limit the likelihood of installing malware.

Identified Developers have certificates from Apple Trusted Vendors that provide a signature of authenticity when the application is installed.

Gatekeeper is a macOS feature that protects against, detects, and blocks malware and malicious extensions. It utilizes file quarantining and code signing to ensure integrity of system resources.

Gatekeeper will warn you if you are about to install an application from an unknown developer. it will NOT open the application and instead will advocate that you move this item into the trash. You will face a prompt that will allow you to bypass this by choosing the 'Open Anyway' option.
- Hack The Box strongly recommends that you do not open or install any application from the web that is identified by Gatekeeper - the origin and security of this item cannot be trusted.

#### Application Privacy

Security measures will ask you before granting permission for an application to use a macOS feature like the camera, microphone, or clipboard.

With default security settings configuration, any applications that are affected by exploits or malicious elements will be sandboxed and are only allowed the privileges you determined.

You should review and modify which applications have access to certain privileges. Hack the Box would recommending checking the privileges for the following system componenets:

- Camera
- Microphone
- Input Monitoring
- Full Disk Access
- Files and Folders
- Screen Recording

#### FileVault

FileVault enables disk encryption for macOS that ensures data cannot be extracted from the system without a password. This setting is toggled on by default if you have Apple silicon. You can find this setting within System Settings > Privacy and Security.

#### Firewall

The firewall protects your OS from possible internet-based threats and can be found within your Network Settings. It prevents your system from being remotely controlled or allowing threat actors to connect to Command Center or Control Center.

By default, the firewall will allow trusted applications to connect to your networked device. Occasionally you will be prompted to permit an application like a VPN or proxy to access the system.

#### Keychain

Keychain is a password management application native to macOS. It can be found via the Keychain Access application or under System Settings > Passwords. 

It allows us to generate random complex passwords across all of your Apple devices. Additionally it can save login credentials for any local or web app, presenting an auto-fill feature whenever we are logging in.

Keychain can also be used to access two-factor authentication keys stored with our passwords. It can auto-fill these generated codes for convenient entry of 2FA codes.

Passkeys are an open standard of password-less login that does not store the true password in any form. This prevents possible password leaks or retrieval via phishing scams, as there is no password present.

Keychain will reveal any weak or repeated passwords to you and prompt you to change them while providing a more secure option. It automatically checks to see if your email address is within leaked password databases and detect if your credentials have been compromised in any way.

#### Find My Mac

Find My Mac is a feature that can be toggled by going to System Settings > Apple ID and selecting Find My Mac. This allows you to locate your Mac device in the case that it gets stolen - even if the device is offline with no internet connection.

If you think your device has been stolen, you can choose to lock the device or erase all content remotely. When an Apple device is marked as stolen, it cannot be sold or used by another user.

#### iCloud Private Relay

The iCloud Private Relay serves as a built-in VPN service that encrypts your internet traffic and browsing history, and hides your IP address. 

This can increase your security presence online and reduce the number of scam and spam information you receive. This service uses two hops to encrypt traffic, so not even Apple has complete visibility of your online activity.

Disadvantages to using the Private Relay means slower internet speeds, incorrect location details, and interference with remote services like Git and Docker.

#### Hide My Email

Hide My Email allows users to create single-user email aliases that forward to your real email address. You can use them with online services and applications that require email for registration without enrolling your true email into their mailing lists. This can be turned on in the Apple ID tab.

#### Advanced Data Protection

iCloud is a powerful tool for remote data storage but at the cost of data privacy. While this is very convenient, it is often not protected by end-to-end encryption meaning that your data can be extracted if required by law. Additionally it could be used for AI training purposes.

iCloud Keychain and Apply Pay are protected by end-to-end encryption, while it should be noted tat iCloud Drive and iCloud Photos are not. This is so Apple can restore data if we forget our iCloud password - if they encrypted it this information would not be able to be retrieved as Apple would not be able to decrypt it.

Apple eventually allows for end-to-end encryption of all data stored in iCloud, allowing for the secure storage of sensitive information and images. You will permanently lose this information though if forget your password or lose you recovery key / contact.

#### Lockdown Mode

Lockdown Mode is a 'locked' version of macOS that disables unnecessary services and limits others such as messaging or online browsing. Third-party applications are also blocked in lockdown mode.

This is used to protect high-profile mac users from cyber attacks like macOS 0-day attacks. Lockdown mode can be enabled via System Security > Privacy and Security. Most people will never turn this feature on.

#### Recommended Security Apps

KnockKnock is a tool that scans your macOS locations where malware is most likely to reside. It will detect the malware and then prompt you to delete it. This tool is made by Objective See, a non-profit foundation that creates free and open-source security tools for macOS.

BlockBlock is another tool made by Objective See that actively monitors locations and requires approval for installation into any persistent directories.

LuLu os another tool by Objective See that monitors connections and prompts users whenever an application attempts to open a novel connection.

Netiquette is a tool that shows all active inbound and outbound connections while checking for malware. 

These tools offer a greater level of security but are also very inconvenient as they will constantly prompt you about many common tasks. If this is of annoyance to you, you can manually run or schedule checks via KnockKnock and Netiquette.

### macOS Terminal

macOS is based on the Darwin kernel that is based on the original Unix OS. This means it will feel familiar to many Linux distributions as they share components in the core shell. 

It should be noted that macOS is an officially certified UNIX operating system, while Linux is based on Minix and defined as UNIX-like. Minix served as an attempt to emulate the UNIX os without using their code, thus avoiding licensing.

POSIX commands will work on both of these operating systems if the related Bash scripts are denoted as \[#!/bin/sh]. This indicates that the scripts are POSIX friendly. This is a key reason why many pentesting scripts are written in POSIX - it makes them compatible with most UNIX systems.

-----

In macOS Terminal you can use the 'open' command to open any file with it's designated default application.

#### ZSH 

macOS transitioned from using Bash to ZSH to provide a more versatile and user-friendly interface with more shell extensibility. The main benefit of using ZSH is the extensions.

If you would prefer to use Bash instead of ZSH, use the following command:

>chsh -s /bin/bash

If you are using an older version of macOS and want to install ZSH, use the following command:

>brew install zsh
>chsh -s /bin/zsh

When you press tab in ZSH after a command - it will show all possible options and arguments below the current line and allows navigation among them using additional tab presses.

You can parse through the command history by pressing the up arrow. If you have entered text into the Terminal field before pressing the up arrow, ZSH will only display entries that contained that text.

##### ZSH Config

When you open the Terminal, a default shell gets loaded with default configurations. By default, the shell is ZSH and the configuration for this is stored within ~/.zshrc directory. This configuration file sets variables and executes some commands to customize the shell. This is also the time when extensions are loaded for the shell.

If you want to implement default configurations, you can use aliases to call them within the shell.

The user that wrote this article uses the following aliases:

>alias ll='ls -l'
>alias la='ls -la'
>alias l='ls -CF'

#### ZSH Plugins

Oh My Zsh is a tool that allows for easy installation and management of ZSH plugins and themes. You can install this with the following command:

>sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

Some plugins are only available via oh my zsh, for example the zsh-syntax-highlighting plugin that adds colors to the shell to denote incorrect commands. This is done by cloning the plugin within the custom/plugins directory under oh-my-zsh.

Install this plugin using the following command:

>git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

You will then need to add the plugin name within the plugin variable in the ZSH configuration file:

>plugins=(zsh-syntax-highlighting)

If you open a new Terminal window, you will see the colors in the shell.

#### Customizing Terminal

For the purposes of the tutorial, this will detail installing the powerlevel10k ZSH plugin/theme via oh-my-zsh. Some fonts will need to be installed to enable icon usage within the terminal. This will install a HTB exclusive macOS terminal configuration.

Begin by installing the required fonts:
- MesloGS NF Regular.ttf
- MesloGS NF Boldf.ttf
- MesloGS NF Italic.ttf
- MesloGS NF Bold Italic.ttf

Next you will install the theme via oh-my-zsh:

>git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

Now add  the following line to the ZSH configurations file:

>ZSH_THEME="powerlevel10k/powerlevel10k"

Once you install, the theme will ask you to configure it during the next terminal boot. For now, wait until the HTB profile has been imported.

##### Homebrew Alternative

You could alternatively download this theme through Homebrew using the following commands:

>brew install romkatv/powerlevel10k/powerlevel10k
>echo "source $(brew --prefix)/opt/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc

### Productivity

Continuity is the key feature of macOS in regard to productivity. It allows you to bring everything from iPhone or iPad right onto macOS. The name comes from allowing continuous use between multiple mac devices simultaneously.

- AirDrop - high-speed peer-to-peer wifi and bluetooth connections for sending files between Apple devices.
- Universal Clipboard - a shared clipboard for any Apple devices on the same Wi-Fi network or within close proximity of one another.
- Handoff - allows you to begin work on one device before switching to another. This is supported by most third party apps.
- Continuity Camera - use an iPhone for a webcam on macOS.
- Sign and Scan with iPhone - scan and sign documents on macOS using an iPhone camera.
- AirPlay / Sidecar - use your apple devices as a secondary display.

