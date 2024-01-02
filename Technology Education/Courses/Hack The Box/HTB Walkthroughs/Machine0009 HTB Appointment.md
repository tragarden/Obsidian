# HTB Appointment

This *Virtual Machine* ( #VM) demonstrates how to use #SQL Injection to exploit an SQL #Database through a web application. Databases store information in tables, and **SQL injection can be used to bypass the protections against accessing tables**. Exploiting the database may yield information such as emails, account names, contact information, purchase data, and credit card information. 

**SQL databases will accept log-in credentials and parse them into the database where it will attempt to match the credentials with stored entries**. ***If there is a confirmed match, the service will return a cookie or token to log the user in and authenticate them*** for access. The web application will grant permissions via cookie or token that is stored locally in the client browser and the webserver.

We are intending to gain access to any web page related to the database that can receive SQL Statements, allowing us to perform the SQL injection exploitation. 

### Preventative Measures

Known techniques for **preventing SQL injection attacks** include a *Web Application #Firewall* ( #WAF),
**input validation or sterilization, parameterized queries, or stored procedures**. In many cases there are weak defenses against SQL injections, making it one of the biggest threats on the #OWASP list of vulnerabilities. 

### Enumeration

#### nmap

We can #ping the target to verify connection status before moving on to our #nmap scan. In this example we will **use a new flag, -sC, to run scripts on the active ports**. ***This is a more invasive or "noisy" method of scanning*** that is more susceptible to triggering a security system in the #network. 

We will **use the following command to run scripts and reveal service versions** with our scan:

>sudo nmap -sC -sV 10.10.10.10

This will **reveal that #port 80/tcp is open running the #http service**. This service is **version 2.4.38 (Debian)** running an #Apache #httpd #server. 

#### Apache


The Apache server is a #FOSS application that may be running a virtual or physical web server. While this is **running on port 80 - ports 443, 8080, and 8000 are also common**. 

#### CVE 

Since we know the version of Apache running the server, we can **lookup the version number in vulnerability databases in hopes that we can find #CVE vulnerability documentation** with known exploits. In the case of this example however, we do not find a relevant vulnerability.

#### Browser

Since we didn't find any useful #CVE documentation for exploiting, we can **attempt to access the server via the #IP address of the target host**.

### Brute-Force (Optional)

When we type the #IP address of the host into our #URL bar **we are presented with a log-in form**. There are many directories on web pages that provide a variety of resources we can exploit, such as administrator and user log-ins, configuration files, images, and code related to #HTML, #CSS, #JavaScript, and #PHP. 

#### URL Modification

Many web pages use a **standardized nomenclature for certain pages** most websites include, such as: **Home, About, Contact, Register, Admin,** etc. While we might be directed to a .com/home page with limited links or navigational options, we may be able to change the word (domain) at the end of the URL to gain access to unprotected pages.

For example we may be directed to the following page by default:

>\https://www.hackmyheadoff.com/home

If we **change the last term**, we may be able to gain access to a different page:

>\https://www.hackmyheadoff.com/contact

You may even be able to identify and **gain access to a nested directory** like below:

>\https://www.hackmyheadoff/contact/admin

#### Status Codes

We will know if these pages exist or not based on the #HTTP **Response Status codes that are returned when we try to access a page**. Typically we will get a respond of 200 OK if the page is available, or 404 Not Found if the page doesn't exist.

#### Gobuster 

While we could manually submit URLs in this way, it is much easier and more thorough to use a #brute-force application such as #GoBuster or #DirBuster with a relevant word list to enumerate web pages. The **wordlist will contain many common directory names and Gobuster will affix these terms to the end of our known #URL**. It will attempt to view a page and then **decide if the page is valid based on what status code is returned**. 

Please note that this method is common and known as a 'noisy' means of #enumeration that is ***often detected by security features***.

Gobuster is written in #Go / #Golang - a #FOSS coding language created by #Google that is extremely fast. It uses a syntax similar to #C language and allows for #multithreading. 

##### Installation

We will **install the Go compiler from the Go language website**.

After successfully installing Go, we will **install Gobuster** with the following command:

>go install github.com\/OJ/gobuster/v3@latest

***Alternatively you could clone the repository and build from source code via***:

>git clone \https://github.com/OJ/gobuster.git

A Gobuster folder should have been created in your current directory. Once you are in the directory with the proper gobuster files, issue the following command to **pull any gobuster dependencies**:

>go get && go build

This will generate the gobuster binary, you may choose to **install it into the Go binary folder $GOPATH/bin**:

>go install

##### Building

We will then use the following commands to **use the build scripts**:

> make

- For #Linux:

>make linux

- For #Windows:

>make windows

- For ALL builds:

>make all

#### Other Commands


To **clean out the build folder**:

>make clean

To run the tests:

>make test


As with other services and applications we have used, it is always useful to **view the help page**:

>gobuster --help

This will show us the commands relevant to gobuster, their syntax, flags, and a description of what they do.

##### Wordlist

You can supply any wordlist that you like and there are many recommended lists supplied with Parrot OS under the directory /usr/share/wordlists. Alternatively you could download what is available from SecLists [here](https://github.com/danielmiessler/SecLists 'SecLists wordlists download').

You can also **download it** with the following command:

>git clone \https://github.com/danielmiessler/SecLIsts.git

#### Using Gobuster

We can **use gobuster with our wordlist** of choice with the following command:

>gobuster dir --url \http://10.10.10.10/ --wordlist /path/to/wordlist/directory-list-2.3-small.txt

In the above command **we use 'dir' to perform web directory enumeration**, --url to supply the URL we are attacking, and --wordlist to select the wordlist for our attack. 

In the case of this machine, using Gobuster did not yield anything useful.

### Further Enumeration

#### Default Credentials

We can now try to **guess default credentials manually** in hopes they are poorly configured.

Try the following credentials:

>admin:admin
>guest:guest
>user:user
>root:root
>administrator:password

None of these were successful login credentials. ***There is the option of brute-forcing credentials, but this is a time-consuming and easily identified means of attack***. We will instead choose to move on to our SQL injection attempts.

#### SQL Injection

If our target website is poorly configured, it is likely vulnerable to SQL injection attacks. We can **exploit the commenting style of #PHP using hashtag characters (#) in our injection** methods. We will **modify our query ( $sql) via the log-in form** if the form is not sterilized or otherwise configured correctly. 

We can **supply the following injection** to manipulate the query submission:

>Username: admin'#

The **hashtag will comment out any SQL language that is beyond the word 'admin'**, ***bypassing the credential checking aspects of the code and allowing us to search the database for the term 'admin'***.
If this is successful, the **$count variable will return '1' which will then return 'true' for the if statement that confirms correct credentials**. We are now able to access the administrator account without submitting a password.

**Enter anything into the password field** to gain access to the administrator account. Once we log in we are presented with the flag for this machine.

### Related:

- [0001 CodeCademy GO](0001%20CodeCademy%20GO.md)
- [024 SQL Injection](024%20SQL%20Injection.md)
- [0719 HTB Web Applications Intro](0719%20HTB%20Web%20Applications%20Intro.md)
- [0728 HTB Web Enumeration](0728%20HTB%20Web%20Enumeration.md)
