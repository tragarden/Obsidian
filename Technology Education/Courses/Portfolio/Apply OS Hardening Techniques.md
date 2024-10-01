You work for the website yummyrecipesforme.com and are investigating a security issue visitors experience when visiting the page. You will identify, document, and remedy this by looking at tcpdump logs.

Identify the network protocols that connect the user to the site.

The site is the victim of a brute-force attack perpetrated by a disgruntled former employee. They gained access to the administrator account, then accessed the admin panel and changed the source code for the site by embedding a JavaScript function that prompted visitors to download and run a file anytime they visit the site. This file redirects the visitor to a fake version of the site that provides the recipes for free. 

This led to many visitors emailing the help desk of the company saying that the website name changed after they downloaded the file, which also caused their computers to run slower.

When the admin tries to log in, the credentials have been changed and they are no longer granted access. 

You create a sandbox environment  to observe the site behavior and run the network protocol analyzer tcpdump. The logs show the following:

1. browser requests DNS resolution for yummyrecipesforme.com
2. DNS replies with the correct address
3. HTTP request is initiated
4. browser initiates malware download
5. browser requests a second DNS resolution and returns greatrecipesforme.com
6. DNS responds with a new IP
7. HTTP request is initiated for the new IP

An analyst checks the source code for the site and recognizes that a JavaScript code has been added that prompts users to download the malware executable.  This is a script that redirects the browser to the new imposter site. It is determined that the default credentials were used for the administrator account and there were no controls in place to prevent this brute force attack.

Document the incident by identifying network protocols and recommend security measures that will address this problem in the future.

### Incident Report

The Protocol exploited in the incident is HTTP which is evident based on communications on port 80. The initial request for the URL yummyrecipesforme.com sent to the DNS server via port 52444 for lookup is returned successfully. The client receives the IP of the site from DNS server IP 203.0.113.22. 

The client then sends a connection request indicated by the S flag using port 36086 to the site yummyrecipesforme.com. This displays the .http suffix on port 80 indicating that the HTTP protocol is being used. The connection request is received as indicated by the S. flag. This request has a slow return that takes about 2 minutes to complete, which is suspicious. There is an extended wait before initiating the next DNS request.

After the pause there is a log entry "\HTTP:GET/HTTP/1.1" which indicates that the browser is retrieving data from the site via the \HTTP:GET method version 1.1. This is suspected to be the downloading of the malware executable file.

After the suspected file download, there is dramatic changes to the output of the tcpdump logs indicating the use of different ports and a change of the domain name URL from yummyrecipesforme.com to greatrecipesforme.com. The DNS server then reroutes the connection to a new IP 192.0.2.172 which is associated with this new URL name. This change in routing indicates the presence of a spoofed IP address and subsequent redirection to the imposter site.

This attack occurred at the application layer of the TCP/IP model.

To remediate this problem, it is suggested that once the administrator regains access to the admin page that default credentials are immediately replaced with new unique credentials with a strict password policy that enforces strong password uniqueness and limited attempts. Once this is completed, it is further advised that the site uses a CAPTCHA on the login page to prevent future brute force attacks. It is also recommended that the admin login requires Multi-Factor Authentication to gain access to the admin console to create multiple layers of security. 