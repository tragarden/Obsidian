# Windows Security Settings 2.5

### Security Settings 

#### Login Methods

There are *three types* of login methods that #Windows is able to authenticate:

- *Local* accounts – these are associated with the device they were created on.
- #Microsoft accounts – these work on all windows machines and sync #Skype, #Office, and #OneDrive.
- #Windows #Domain accounts – these are centrally managed from the *Active Directory.*

Users are the existing accounts on the machine including the #Administrator, **Guests, and Standard Users.**

*Groups* contain selections of users and organize them by their #permissions and actions.

*Login options* accepted by Windows include **Username / Password, PINs, Biometrics, facial recognition, fingerprint, security keys, picture passwords, and #SSO.**

#### Single Sign-ON

*Single sign-on* ( #SSO) will allow you to **log in one time with Windows #Domain credentials,** and for the rest of that session you will be able to use other devices and files that accept Windows Domain credentials.

#### NTFS

#NTFS #permissions are **applied from local and #network connections,** **while share permissions only apply to network connections and is otherwise known as a ‘network share’.**  If both of these are actively being used, the one with more restrictive rules will assume priority over the less restrictive one.  

So, if #NTFS has full #permissions **but Share permissions are limited to ‘read only’, then we will resultantly only be able to read information.**  ***NTFS inherits its permissions from the parent*** object it is contained within.  You can bypass any restrictions by putting NTFS or share into a different volume with a pointer telling windows where it is stored.

Explicit permissions are the default permissions set for a *network share.*

#Inherited **permissions come from** the #parent object – in the case of a folder, all permissions of the folder will be the default permissions assigned to any files within the folder.

#### Administrator

*‘Run as Administrator’* is an option in #Windows that you will **use any time you need elevated permissions,** for instance when you are managing system files or installing new services.

#### User Account Contols

*User Account Controls* ( #UAC) is a way to **manage standard users on your network by limiting their access and permissions.**

The #UAC may pop up for #dministrators when **installing applications or configuring remote desktop technologies.**

#### Secure Desktop

A *Secure Desktop* window will appear when you are making changes to the operating system – it will clearly describe what is about to happen and the potential consequences that you may face if you persist.

### Encryption

#### BitLocker

#BitLocker is used to #encrypt the #volumes on your system, effectively **protecting all of your data including information related to the #OS.** In the case that you lose your device, or it fails, you will be able to recover your data.  BitLocker To Go is used to encrypt #USB flash drives.

#### EFS

*Encrypting File System* ( #EFS) is used to **encrypt everything within the NTFS** file system on all versions of Windows except Home.  There will be a username and password associated with the encryption key.  If your administrator does a reset on your hardware, you will lose access to all EFS files.

### Related:
- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1102/220-1102-video/windows-security-settings-220-1102/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [025 Windows Firewall](025%20Windows%20Firewall.md)
- [015 Windows Settings](015%20Windows%20Settings.md)

#study #professormesser #comptia #Aplus #software #activedirectory 