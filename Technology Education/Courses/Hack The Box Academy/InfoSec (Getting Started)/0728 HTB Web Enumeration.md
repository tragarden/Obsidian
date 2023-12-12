# Web Enumeration

Web Applications offer a large attack surface with high-value targets and this must be considered when we are exploring and searching for attack vectors. There are a variety of programs and tools we can use to enumerate the possible 

### Tools

#### GoBuster

#GoBuster and #ffuf are tools that perform #directory #enumeration on a web application. This is useful for uncovering hidden files and directories that lead to privilege escalation or sensitive information that is not secure.

GoBuster allows us to use a dictionary attack to brute-force various target types such as #DNS, #AWS buckets, #vhost, files, and directories. 

We can use the following command to use GoBuster to apply a wordlist brute-force attempt to a given #IP address:

> gobuster dir -u http://10.10.10.121/ -w /usr/share/dirb/wordlists/common.txt


#### DNS Subdomain Enumeration

A #Subdomain refers to administrator portals or hidden apps within a web application that may contain vulnerabilities and sensitive resources. 

##### Installing SecLists

The following commands will clone and install the repository for #SecLists from Daniel Miessler:

> git clone https://github.com/danielmiessler/SecLists

> sudo apt install seclists -y

Next we will use GoBuster to add a #DNS server to the /etc/resolv.conf file.

> gobuster dns -d inlanefreight.com -w /usr/share/SecLists/Discovery/DNS/namelist.txt


#### Banner Grabbing

Banners, also known as Web Server Headers give a brief summary of what is being hosted on a given web server. A tool that can be useful for banner grabbing is #EyeWitness, which allows you to screenshot web applications and create a digital fingerprint of the app.

We will once again use #cURL to grab the banner with the following command: 

> curl -IL https://www.inlanefreight.com


#### Whatweb

The #Whatweb tool is used to analyze a web server and return information about the version and frameworks were used to build the application.

An example use of this tool is as follows:

> whatweb 10.10.10.121

If you experience issues:

> whatweb --no-errors 10.10.10.121/24


#### Certificates

We must consider the #SSL / #TLS certificates associated with a given web server if it uses #HTTPS. This will reveal information related to the location of the server, who owns it, associated email addresses, and information about who issued the certificate.

#### Robots.txt

Many sites have a robots.txt file associated with their domain so that web crawlers like Googlebot can easily locate hidden directories and administrator pages. This allows the crawlers to fully evaluate the entirety of the page for the purpose of data collection.

#### Source Code

We can press Ctrl + U while using our browser to view the source code for a site which can reveal information that developers may have forgotten to remove. A common tactic is to locate any comments, as they may yield clues about page design or flaws that have yet to be addressed. 