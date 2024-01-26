# Metasploit Modules

#Metasploit modules are scripts that contain functions for specific exploitation purposes that have been tested in real-world scenarios and known to work. These are Proof-of-Concept ( #POC) exploitations that automate the targeting of known vulnerabilities. 

#### Automation vs Manual Exploitation

There are many cases where the Metasploit framework is used and the given module for an exploit fails, leading people to believe that the module does not work. In this case however, correlation is not causation. There are many nuances to applying an exploitation and this often requires intervention from a knowledgeable user. There may be modifications or tweaks to the exploit required for it's success. Automation is useful for quick assessments and support but will always be less viable than the manual application of a user skilled in exploitation.

### Syntax

The syntax for executing a module is as follows:

>\<No.> \<type>/\<os>/\<service>/\<name>

An example of an executable command would be as follows:

>794 exploit/windows/ftp/scriptftp_list

The various parts of the command can be interpreted as the following components:

#### Index Number (No.)

The index number selects the specific module by using the 'No.' tag.

#### Type

The type tag is used to segregate Metasploit modules and is the first level of segregation applied. This is implemented to facilitate modularization and there are various types:

- Auxiliary - scanning, fuzzing, sniffing, and administrator capabilities that extend function.
- Encoders - ensures payloads remain intact during transmission.
- Exploits - exploit vulnerabilities and allow delivery of payloads.
- NOPs - (No Operation Code) maintains consistent size of payloads.
- Payloads - remote execution that returns to the attacker machine via shell.
- Plugins - scripts that can coexist and integrate with msfconsole.
- Post - information gathering modules.

The 'use \<no.>' command is only compatible with the Auxiliary, Exploits, and Post categories. 

#### OS

Indicates the operating system ( #OS) being used on the target host.

#### Service

The service tag indicates the vulnerable service on the target machine. This is often used for gathering credentials and data.

#### Name

The Name tag indicates the action performed and the purpose of the module.

### Searching

The search feature for msfconsole is robust and is quite useful at managing the default modules. Type 'help search' within msfconsole to learn about this detailed and nuanced aspect of the applicaton.

#### EternalRomance Example

If we know the name of a known vulnerability, we can simply search for the exact name. 

Use the following command to search for the EternalRomance vulnerability in the msfconsole module data:

>search eternalromance

#### Specific Searching

If searching for the exact name a vulnerability is not applicable in your case, there are methods of searching in a more broad way. We can search for years the vulnerability occurred (cve:\<year>), operating system (platform:\<os>), module type (type:\<auxiliary/exploit/post>), reliability rank (rank:\<rank>), and the search name (\<pattern>).

An example of this type of search is illustrated in the following command:

>search type:exploit \platform:windows cve:2021 rank:excellent microsoft

### Selecting Modules

We can select modules after determining available vulnerabilities using basic enumeration techniques.

Use the following command to enumerate a target host to determine known vulnerabilities:

>nmap -sV 10.10.10.10

In the example given, this scan returns information that reveals the target host is running an outdated version of #SMB that is vulnerable to the EternalRomance Exploits for MS17_010. SMB server is open on port 445.

Now we can run the following command in msfconsole to search for vulnerabilities related to ms17_010:

>search ms17_010

This reveals four variants of the EternalRomance exploits - we will want to find the appropriate variant for exploiting Windows 7. In the case of the example this would be Index no. 2 provided by the search feature in msfconsole. Running this instance of the exploitation can test if the target is indeed vulnerable to this variant.

### Implementing Modules

We can select our variant by submitting a command indicating the index of the variant. 

Use the following command to activate the vulnerability with index 0:

>use 0

We can then see a list of related information by submitting the options command:

>options

This will reveal a detailed list of the setting related to the vulnerability with a description. There will be a list for Module options, as well as a second list for Payload options. There is also a 'Required' column for both sets of options - this tells you which information or configurations you must apply before you can use the exploit. Any parameter with 'yes' in the required column is mandatory. 

We can return even more verbose output about our exploit with the info command:

>info

Info will return basic set of options as well as a detailed description and list of resources and documentation to expand your knowledge. This information will help you determine if this exploitation is right for your specific scenario. 

### Target Specification 

In order to configure our exploit to attack the correct target, we must assign values to the RHOST or RHOSTS variabled to indicate the address of our target host.

If we know the #IP address of the target host, we can supply it to our RHOSTS variable with the following command:

>set RHOSTS 10.10.10.10

#### Semi-Permanent Target Specification

If we know we will be working with the same target host via multiple modules during a session, we can specify this with the 'setg' command - this will set the target host variable RHOST or RHOSTS for the duration of our console session.

Use the following command to set the RHOSTS value to the target host for the duration of the session:

>setg RHOSTS 10.10.10.10

### Target Interaction

Once we have set our RHOSTS values to the target host, we can execute our exploit and gain control of a shell on the target machine. Once a shell has been established, we can begin to interact with the target host by issuing commands. 

>run

A good place to start when you have successfully initiated a shell on the target is the 'whoami' command:

>whoami

