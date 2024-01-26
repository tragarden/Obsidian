# Metasploit Targets

Targets are unique identifiers within the Operating System ( #OS) that an exploitation module has been developed for. 

The 'show targets' command within the exploit module reveals all vulnerable targets for the given exploit. This will not work if you execute this command in the root menu outside of a designated module - you must select an exploit module first.

### Selecting Targets

In the example given, we are working with the MS12-063 Microsoft Internet Explorer execCommand Use-After-Free Vulnerability. One of the first commands we should be issuing after selecting an exploit is the 'info' command. You will need to become familiar with the module and exploits functionality.

Once you have selected this exploit, use the 'info' command to reveal detailed information about the exploit:

>info

Next, use the 'options' command to understand what this exploit will do when we use it and what versions are vulnerable to this exploit.

>options

In the case of our module, you will see that exploits exist for both various verisons of Internet Explorer and various versions of Windows. You will need to select the ID that is associated with the version of both #IE and #Windows that matches your target system. You should know this information from the #enumeration stage, but you can choose the 'Automatic' ID to configure the exploit automatically using built-in detection features. This will perform service detection on the given target.

Use the show targets command to reveal the list of relevant IDs:

>show target

Then, choose the Exploit ID that matches your target system:

>set target 6

The address returned may be a 'jmp esp', a jump to a specific register identifying the target, or a 'pop/pop/ret'.  ( NO IDEA WTF THIS MEANS LOL). 

To correctly identify a target, you will need to:

- obtain the target's binaries
- use msfpescan to locate a return address