# BIOS Settings 3.4

### Manufacturer Standards

Each manufacturer has a secret button that they use to access the #UEFI while booting your computer.  **Delete, F1, F2, Ctrl-S, Ctrl-Alt-S, or other F keys** or button combinations.  #Hyper-V for #Windows (2011+) allows you to manage windows features.

UEFI #BIOS **simulators are available online** for you to explore and practice with, without endangering your operating system. 

### Fast Startup for Windows

*Fast Startup* is a feature for Windows 8, 10, and 11 that puts your computer into a **hibernated state instead of a complete shutdown**.  It **boots so quickly that you will not be able to open the BIOS** before it boots. To bypass this, you must ***hold down the shift key when you are clicking the restart button*** on the GUI.  An alternative to this is to **interrupt the system boot three consecutive times**, which will render the UEFI available. 

If you wish to ***disable Fast Startup***, go to Settings > Updates & Security > Recovery > Advanced Startup > Restart Now.  Alternatively, this can be done from the #OS terminal via the ‘msconfig’ command. 

When your BIOS configuration is complete – ***TAKE NOTES OR A PICTURE*** of your configuration as backing up this information is **vital to recovering your system**.  DO NOT make changes unless you have full comprehension about what will happen when you do.

### Boot Options

#Boot options allow you to **disable and enable system hardware**.  You are also able to **prioritize hardware for the boot order**, choosing whether the system boots from USB, SSD, or HDD.

#USB permissions are a ***major security concern*** as these are one of the most common devices used and one of the most insecure.  This must be managed with diligence and attention.  These permissions can be set via the ‘Devices’ tap in the setup menu of your UEFI. 

FUN FACT: The **US Department of Defense banned all USB Flash media from 2008-2010** after getting infected with the #SillyFDC Worm that infiltrated the entire network of the DOD. 

### Cooling and Fans

Fans are a vital piece of hardware for any computer system, as they generate a lot of heat while they are performing.  There are fans mounted to the chassis of the computer tower, as well as individual fans built onto the #CPU and #GPU hardware.  **Most motherboards have a fan control integrated into their design**, monitoring temperatures, and increasing or decreasing the fan speed accordingly.

Your BIOS may have options for *Intelligent Cooling*, which allows you to tailor your fans to your preferences.  There is usually an option for Best Performance – high speeds, Best Experience – quiet speeds, or Full Speed which keeps the fans set to their max speed.

### Secure Boot

*Secure Boot* is part of the UEFI interface and is used to **protect against #malware that may be able to change your BIOS settings**, compromising the security of your system.  With Secure Boot, ***software will not be able to run until a cryptographically secure digital signature is received by the UEFI***, confirming that the software is safe to run, and no malware has made modifications to your configuration settings.   Secure boot can be **disabled under the security tab of your BIOS** setup menu.

UEFI BIOS protections involve the **manufacturer’s public key in conjunction with a digital signal that is checked during updates**.  This BIOS feature will **prevent unauthorized writing to flash storage**.  Secure Boot verifies your bootloader, which is examined for a digital signature.  The **bootloader is then signed with a certificate** ensuring that the digital signal is authentic.

You can add a user #password to your BIOS that will require you to enter this password before you can access your operating system.  A **supervisor password can also be enabled**, making sure a password must be entered before you can make BIOS configuration changes.  ***DO NOT forget these passwords***, as they are not in your OS, they are in BIOS and will need to reset your BIOS to access the system again.

The BIOS configuration settings and passwords get saved to the same flash memory that your system reads the BIOS boot info from.

### Battery Backup

*Complementary Metal-Oxide Semiconductor* ( #CMOS) is a type of #memory that is **backed up with a battery**.  These BIOS systems can be **reset via removal of this battery**. This is an older method of storing bios memory, today we use flash memory as it does not require battery backup making it more reliable.  As a last resort, you can **reset the BIOS by shorting two pins** on the #motherboard with a jumper.  It may be labeled ( #CLRTC) *Clear Real-Time Clock*.

### Cryptography

*Trusted Platform Module* ( #TMP) is hardware that **helps cryptographic functions** in your system.  If your drives are encrypted, this is a very important feature as it will be used to **create a cryptographic key to decipher the encryption on the drives**. The **TPM includes a processor that uses a random number generator** as a key generator.  These devices have **persistent memory, which is used long-term to access unique keys** that were burned into the hardware.  These devices **store data about storage keys and hardware configurations** in versatile memory.  It is also **password protected** against dictionary and brute-force style attacks.

#### Cryptographic Load Balancing

*Hardware Security Module* ( #HSM) is something used to monitor and manage large technology environments.  It may come in the form of a **standalone-unit, rack unit, or expansion card**.  It has **secure storage for servers and has key backup** that is useful, because no single person can have access to these keys, only the HSM manages them.  Light duty HSMs can be **stored on USB, flash, or Smart Card** memory types.  This device has a **form of load balancing for cryptographic traffic**, allowing servers to forward some of their cryptographic processing to the HSM.

### Related:

- [Professor Messer](https://www.professormesser.com/free-a-plus-training/220-1101/220-1101-video/bios-settings-220-1101/ "Professor Messer A+ Guide")
- [CompTIA](https://www.comptia.org/ "CompTIA Homepage")
- [CompTIA A+ with James Messer](CompTIA%20A+%20with%20James%20Messer.md)
- [022 Wireless Encryption](022%20Wireless%20Encryption.md)
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [029 Securing a SOHO Network](029%20Securing%20a%20SOHO%20Network.md)
- [021 Physical Security](021%20Physical%20Security.md)
- [031 Troubleshooting Solutions](031%20Troubleshooting%20Solutions.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [032 Troubleshooting Security Issues](032%20Troubleshooting%20Security%20Issues.md)
- [053 Troubleshooting Storage Devices](053%20Troubleshooting%20Storage%20Devices.md)
- [053 Troubleshooting Storage Devices](053%20Troubleshooting%20Storage%20Devices.md)
- [534 The BIOS](534%20The%20BIOS.md)

#study #professormesser #comptia #Aplus #hardware #secureboot 