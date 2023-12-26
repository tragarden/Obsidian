# Privilege Escalation

While we may be able to access a target it is unlikely that we will have the desired administrator or root privileges that we need. This means that we will have to be thoughtful and strategic about how we gain access to administrator accounts so we can acquire execution rights.

### Enumeration

#### Checklists

There are many facets to consider during the enumeration process. Discovering and tracking available vulnerabilities is a key part of the penetration process. There are many things to consider and we often overlook at least a few of these things. Luckily there are #PrivEsc checklists available that denote all the possible avenues for penetration. [HackTricks](https://book.hacktricks.xyz/ 'HackTricks Privilege Escalation Checklist') and [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings 'PayloadsAllTheThings Privilege Escalation Checklist')are both useful lists for both #Linux and #Windows. 

#### Scripts

Using a #Script to enumerate an operating system is a common way to begin penetration testing. There are applications we can use to quickly perform many enumeration techniques with a single command. Common enumeration scripts for #Linux include [LinEnum](https://github.com/rebootuser/LinEnum.git 'LinEnum Enumeration Scripts for Linux')and [linuxprivchecker](https://github.com/sleventyeleven/linuxprivchecker 'linuxprivchecker enumeration scripts for Linux'). Common enumeration scripts for #Windows include [Seatbelt](https://github.com/GhostPack/Seatbelt 'Seatbelt enumeration scripts for Windows')and [JAWS](https://github.com/411Hall/JAWS 'JAWS enumeration scripts for Windows'). We can also use [Privilege Escalation Awesome Scripts SUITE](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite 'PEASS enumeration scripts')which is also known as #PEASS.

Here is an example of a command using the  PEASS script LinPEAS:

>./linpeas.sh

#LinPEAS will run, displaying the collected information in a neatly organized report.

#### Kernel 

#Kernel exploits are useful when we access a machine that uses an outdated version of an operating system or a version that is beyond it's End-of-Life ( #EOL) terms. When we uncover an outdated kernel, we can simply perform a web search for the known vulnerabilities for a given kernel. Please be mindful that exploiting a kernel can destabilize a working operating system, so we should experiment with these exploits in a #VM before exploiting an actual target.

#### Software

If we discover outdated software on a system it can be used for exploitation and privilege escalation. We can look in the C:\\Program Files folder of a Windows machine or enter the following command to see the software installed on a Linux machine:

>dpkg -l

Once you have identified the installed software, you can look up the common exploits related to that software and the version your target is using.

#### User Privileges

Sometimes the user account we gain access to has privileges that allow us to execute. We can determine our privileges with a few sample commands, such as #sudo, #SUID, and Windows Token Privileges.

##### Sudo

The Superuser ( #sudo) command in #Linux allows us to execute commands as the super user, or #root user. This is often associated with a set list of commands, but sometimes has extra control. 

We can see what privileges are available to sudo with the following command:

> sudo -l

If the result for this command specifies "ALL". then we have complete control over the system. 

We can use sudo to switch to the superuser account with the following command:

>sudo su -
>\[password]
>whoami
>root

If you do not know the password for the superuser, you may be able to discover directories and files that do not require a password using the following command:

>sudo -l | grep "NOPASSWD"

The above command will show us any users that have access without requiring a password. The user 'user' has access to the directory /bin/echo

We can supply user credentials to gain access with the following command:

>sudo -u user /bin/echo Hello World!

We can use the above techniques to determine vulnerable users and vulnerabilities with the sudo command. A site like [GTFOBins](https://gtfobins.github.io/ "List of sudo vulnerabilities")lists the known sudo commands that are vulnerable. [LOLBAS](https://lolbas-project.github.io/# 'LOLBAS Windows Privilege Escalation')can be used to find vulnerabilities in Windows machines.

#### Scheduled Tasks

Scripts can be scheduled to run at specific times in both #Windows and #Linux operating systems. In most cases we can escalate privileges and create new scheduled tasks.

In Linux systems, #Cron Jobs is the method of creating and maintaining the scheduling of tasks or scripts. We must obtain write permissions for the cron directories in order to create new jobs and thusly implement a reverse shell command.

The directories we need write permissions for are:

>/etc/crontab
>/etc/cron.d
>/var/spool/cron/crontabs/root

#### Exposed Credentials

We can use enumeration scripts to look for stored credentials within configuration files, log files, and user history. For Linux the user history is found within 'bash_history' and on Windows machines the user history is found within #PSReadLine.

Password Reuse is another place we can investigate to discover exposed credentials.

#### SSH Keys

SSH keys are a vulnerable target because we would only need read permissions to read the passwords / keys. If we have access to the .ssh directory, we should be able to read the private SSH keys for the user.

The private SSH keys should be found within:

>/home/user/.ssh/id_rsa  
>/root/.ssh/id_rsa

If we have access to those directories, we can use the following command to read the keys, copy the key, and use the -i flag to log in with the credentials:

>vim id_rsa
>chmod 600 id_rsa
>ssh user\@10.10.10.10 -i id_rsa

The chmod 600 id_rsa command above will increase the restrictions on the id_rsa directory, which are often weak by default.

After gaining access to a user's .ssh directory and open a shell as that user, we can create a new public key in the user's directory so ensure our own access:

>ssh-keygen -f key

The above command will generate a file that contains the new key called key, and the key.pub file containing the public key. 

We will place the key.pub file in the remote machine and add it to the directory /root/.ssh/authorized_keys:

>echo "ssh-rsa AAAAB...SNIP...M= user@parrot" >> /root/.ssh/authorized_keys

Now you can log in with the private key to gain root access:

>ssh root@10.10.10.10 -i key

