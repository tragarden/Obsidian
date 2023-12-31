# HTB Fawn

This *Virtual Machine* ( #VM) is focused on using* File Transfer Protocol* ( #FTP) vulnerabilities to gain access to the target host. FTP is used to easily **move files between networked devices** such as a #server to a #client. **Authentication is achieved via clear-text username and password submission, although anonymous login is often available**. The nature of the clear-text communications and storage of file contents makes this protocol **vulnerable to Man-in-the-Middle** ( #MITM) attacks.

As a standard FTP has encrypted versions for **secure file transfer** - either with #SSL / #TLS ( #FTPS) or #SSH *File Transfer Protocol* ( #SFTP). This interface is **often misconfigured or disabled** to make it easier to use, which leads to vulnerabilities. When using SSH the data transmitted is tunneled, and more secure as a result.

An important note about the concept of **ports is that they allow us to connect more than one service to a given #IP address**. Ports enable us to use multiple streams of network data simultaneously - without them we would not be able to stream music and use a web browser simultaneously. 

### Enumeration

#### Ping

We will begin our #enumeration phase with a #ping command:

>ping 10.10.10.10

**Once we have results** showing we have successfully reached the target, **press Ctrl + C to cancel**. Sometimes we will encounter ***a #firewall that actively blocks pings*** like this, but this system is not using a firewall capable of this.

#### nmap

We will now **perform our #nmap scan with version detection** as the next phase of enumeration:

>sudo nmap -sV 10.10.10.10

This reveals that **port 21/tcp is open and running the FTP #service version 3.0.3 on the #Unix #OS**.

#### FTP

We can now attempt to connect to the FTP service. First we should **ensure that we have FTP installed and updated on our client** before attempting to connect. We do so with the following command:

>sudo apt install ftp -y

Then we can **search through the FTP manual** to determine how to connect to the host machine:

>ftp -h

This will display commands that we can use with the FTP service. We can use the following command to connect:

>ftp 10.10.10.10

We will then be prompted to **submit a username**. We can try the username '**anonymous**' to access FTP **without a password**.

>anonymous
>{any password}

Now **we are connected to the host via FTP**. We can type 'help', -h, or --help to learn the commands associated with FTP. To learn more about any command, type 'man {command}'. We can see that **FTP uses many of the same commands as #Linux** terminal.

If we use the 'ls' command, we can see the contents of the directory we are in. We will also see the status messages of the FTP service as well as the flag.txt file.

Since we cannot use the 'cat' command to read the contents of the file on the host machine, we can **import the file to our client machine using the FTP service**. We can do so with the following command:

>get flag.txt

This will **download the file to whatever directory you executed the FTP service from** on the client device. You can now **exit the FTP service** and run the following command in the same directory to **read the contents of the flag.txt file**:

>cat flag.txt

This will display the contents of the file containing the #hash.