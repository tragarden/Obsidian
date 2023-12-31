# HTB Dancing

This *Virtual Machine* ( #VM) demonstrates how to use *Server Message Block* ( #SMB) vulnerabilities to exploit a target host. SMB is mainly used on #Windows machines to **communicate to serial ports and printers on a network to access files on a remote server**. SMB often runs on #port 445/tcp which is **active on the Application or Presentation layers** of the #OSI model. This #service often runs with the help of #NetBIOS on the Transfer layer of the OSI model. This means that **NetBIOS and SMB may both appear to be running on the hosts ports**.

A file that is stored on a host via SMB is known as a #network #share and can be accessed by clients on the same network. **Authentication for SMB is through username/password credentials and allows the client to access, create, edit, and delete files on the host**.

A ***common vulnerability*** with SMB is if it has been **configured to allow guest accounts or anonymous log-on**. 

### Enumeration

#### Ping

We can **ping this target host** to determine if we can establish a connection:

>ping 10.10.10.10

#### nmap

We can then **perform our #nmap scan with the -sV flag** to determine the version of the services running on the open ports:

>sudo nmap -sV 10.10.10.10

This will reveal that **port 135/tcp is open** and running *Microsoft Windows RPC* ( #msrpc) as well as **port 445/tcp running microsoft-ds**. These services are both **running on Windows** and the microsoft-ds service is the share we are seeking.

#### smbclient

#SMBclient is a script that we can use to further enumerate our target host. 

First we should **make sure that smbclient is installed and updated** accordingly:

>sudo apt-get install smbclient

When **smbclient attempts to connect it will expect a username**, and if one is not supplied then the ***default username of your client will be used***. This is something to **take note of if your are avoiding being discovered** on the target host. In this case it is okay to use our default username since we do not know usernames on the target host. 

Once we are successful in connecting, we can use -h or --help to view the available commands for smbclient. 

We may then **use the the list flag -L to reveal all of the active shares** on the host. 

>smbclient -L 10.10.10.10

This will **reveal four shares** on the host:

| Sharename  | Share Type | Info                |
| ---------- | ---------- | ------------------- |
| ADMIN$     | Disk       | Remote Admin Access |
| C$         | Disk       | Default Share       |
| IPC$       | IPC        | Remote IPC          |
| WorkShares | Disk       |                     |
- *ADMIN$* holds administrator shares which are **hidden shares that allow remote access for administrators. This can be disabled but never deleted**.
- *C$* is the **administrator share for** the default #Windows **drive C:\\**
- *IPC$* is not a part of the file system and is known as the **inter-process communication share**.
- *WorkShares* is ***not a default share*** and was created.

We can now try to **log into each share with generic credentials** to see if we have access. Please note that the ***IPC$ share does not have directories and will not be readable*** to us. 

Use the following commands to **attempt to gain access**:

>smbclient \\\\\\\\10.10.10.10.\\\\ADMIN$

>smbclient\\\\\\\\10.10.10.10.\\\\C$

>smbclient\\\\\\\\10.10.10.10.\\\\WorkShares

WorkShares should be the share that grants us access the the SMB service. We can type 'help' to see the list of commands for this service, which allows basic #Linux commands like ls and cd.

We can **use the ls command to see the available directories** within the share. We can see that there is a **directory for Amy.J and James.P**. Use the cd command to explore these directories. We can see that there is a **file named  worknotes.txt in the Amy.J directory and a file named flag.txt in the James.P directory**. 

We can **use the 'get' command to retrieve these files** from there respective directories with the following command:

>get worknotes.txt
>get flag.txt

We can then **exit smbclient and use the cat command** on these files to read them:

>cat worknotes.txt
>cat flag.txt

This will reveal the hash for the machine in the flag.txt file, as well as ***some valuable information for further exploitation in the worknotes.txt file***.