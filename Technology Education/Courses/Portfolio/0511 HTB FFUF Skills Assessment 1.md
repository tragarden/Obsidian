# Web Fuzzing Skills Assessment

### Scenario

Use an online academy's IP address for Penetration testing. I will locate all pages and domains linked to this IP in order to completely enumerate the IP and domain. Fuzz each page to determine if any parameters can be interacted with and retrieve any data I can from them.

IP and Port are:

>94.237.49.166:48521

### Objectives

1. Run a sub-domain / vhost scan on '\*.academy.htb' for the given IP. What sub-domains are identified?

2. Run an extension scan before a page scan. What extensions are used by the domain?

3. A revealed page states 'You don't have access!'. What is the URL for this page?

4. On the page for step 3, there are multiple parameters. What are they?

5. Fuzz the found parameters for working values. One will return a flag - what is it?

### Methods

#### Adding Domain to Host List

For the first step, I intend on adding the academy.htb domain to /etc/hosts. 

>sudo sh -c 'echo "94.237.49.166 academy.htb" >> /etc/hosts

![[Pasted image 20240325124249.png]]

#### Subdomain Fuzzing

After it has been added to the hosts file, I will scan the sub-domains using the subdomains-top1million-5000.txt wordlist. This can be performed with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \http://FUZZ.academy.htb/

This did not return any valid subdomains for the domain academy.htb.

#### Vhost Fuzzing

Since the Subdomain scan didn't return anything useful, I then decided to fuzz for Vhosts.

I will use the following command to fuzz the Vhosts:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \http://academy.htb:48521/ -H 'Host: FUZZ.academy.htb'

This method returned many results with the HTTP status code 200 and a size of 985. I then decided to filter out these results by including the -fs flag and the indicated size of 985.

![[Pasted image 20240325130836.png]]

#### Filtering

I then used the same command for Vhost fuzzing with the added filter for size:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \http://academy.htb:48521/ -H 'Host: FUZZ.academy.htb' -fs 985

This returned 3 relevant vhost names: 'archive', 'test', and 'faculty'.

![[Pasted image 20240325131112.png]]

This satisfied the requisites for step 1: find the sub-domain/vhost names.

#### Adding New Vhosts

I will now add the newly discovered Vhosts to the /etc/hosts file:

>sudo sh -c 'echo "94.237.49.166 archive.academy.htb" >> /etc/hosts
>sudo sh -c 'echo "94.237.49.166 test.academy.htb" >> /etc/hosts
>sudo sh -c 'echo "94.237.49.166 faculty.academy.htb" >> /etc/hosts

![[Screenshot 2024-03-25 132202.png]]

#### Extension Fuzzing

Next I decided to fuzz the HTTP response headers to determine the extensions used by the server, which may indicate the type of server being used.

I used the following command to fuzz the extensions in the HTTP headers:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u \http://94.237.49.166:48521/FUZZ

This output showed five extensions: .htm, .html, .phtml, .php, and .phps. 

![[Screenshot 2024-03-25 133039.png]]

I found that these results did NOT satisfy the requisites for the module, so I modified my scans to target the vhosts I discovered in the previous step.

I did NOT include the term 'index' in the path for my URL, which made the scan too broad (which is why HTML extensions are present). I modified my scans to involved the subdomains and the index files.

I ran the three following scans:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u \http://archive.academy.htb:48521/indexFUZZ

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u \http://faculty.academy.htb:48521/indexFUZZ

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u \http://test.academy.htb:48521/indexFUZZ

![[Screenshot 2024-03-25 134800 1.png]]

![[Screenshot 2024-03-25 134703.png]]

![[Pasted image 20240325134928.png]]

The results of the extension fuzzing scan on all three vhosts returned the extensions .php, .phps, and .php7. This satisfied the requisites for the module.

Based on this information I could assume that any of the following servers might be used by the domain:

- Apache HTTP
- NGINX

#### Page Fuzzing

Now that I have performed successful enumeration of extensions used by the server, I can now start fuzzing for pages. I will attempt a recursive fuzzing scan to try to enumerate all possible pages and sub-pages.

I will use the following command to perform my recursive scan of the site:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://94.237.49.166:48521/FUZZ -recursion -recursion-depth 2 -e .php -v -ic

I included the -e flag to put commas between list entries for separations purposes.

I included the recursion depth of 2 to limit the length of the scan.

I used the -v flag to indicate that I wanted verbose output that shows full URL names and redirections for the various vhosts.

I used the -ic command to ignore the copyright information at the beginning of the directory-list-2.3-small.txt file.

![[Pasted image 20240325140712.png]]

This scan provided limited results, prompting me to change my scan commands.

## NOTE

***At this point the lease time of the server I was using expired, so the PORT changed from 48521 to 46676.***

#### New Page Scans

I decided to run four scans with the newly generated port number - one for the original domain and then three more for the archive, faculty, and test subdomains:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .php -v -ic

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://archive.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .php -v -ic

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://faculty.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .php -v -ic

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://test.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .php -v -ic

The scans on the domains academy.htb and test.academy.htb did not return any new or interesting information on the first scan for the .php extension. I then set those scans to run with both .php7 and .phps as scan parameters.

The scans on domains archive.academy.htb and faculty.academy.htb both returned the page 'courses' during their first recursive scan for the .php extension. None of the discovered pages provided a message stating 'You don't have access!' as requested by the module.

![[Pasted image 20240325143934.png]]

![[Pasted image 20240325143855.png]]

I continued to let these scans run on their second iteration of recursion.

When the second round of recursive scanning completed on the archive.academy.htb and faculty.academy.htb domains completed, there were no interesting or functional pages revealed.

The additional searches I performed on the academy.htb and test.academy.htb using the .phps and .php7 extensions did not return any results of interest either.

I then performed four more scans using the archive.academy.htb and faculty.academy.htb domains and the .php7 and .phps extensions while filtering out the file size 287:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://archive.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .phps -v -ic -fs 287

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://archive.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .php7 -v -ic -fs 287

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://faculty.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .phps -v -ic -fs 287

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://faculty.academy.htb:46676/FUZZ -recursion -recursion-depth 2 -e .php7 -v -ic -fs 287

The result I was seeking was found within the domain faculty.academy.htb associated with the .php7 extension. 

The URL that leads to the page that states 'You don't have access!' was:

>\http://faculty.academy.htb:46676/courses/linux-security.php7

![[Pasted image 20240325151446.png]]

![[Pasted image 20240325151521.png]]

Now that this URL has been found and the requisite objective has been satisfied, I will fuzz for parameters associated with this URL.

#### Fuzzing Parameters

Now that all hidden pages have been enumerated, I will fuzz for parameters associated with the page we are forbidden from accessing.

##### GET

I will use the following command to scan this URL via GET request:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u \http://faculty.academy.htb:46676/courses/linux-security.php7?FUZZ=key 

This command yielded an overwhelming amount of results that needed to be filtered out by file size. I filtered the results with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u \http://faculty.academy.htb:46676/courses/linux-security.php7?FUZZ=key -fs 774

This scan then returned the parameter 'user' in association with the given URL.

![[Pasted image 20240325152043.png]]

This single result did not satisfy the requisites of the module though, and I needed to perform a POST fuzz scan as well for any other associated parameters.

##### POST

I found the parameter 'user' by using the GET request method of fuzzing parameters, so the next option was to do the same with a POST request.

I used the following command to perform my POST request fuzz scan:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u \http://faculty.academy.htb:46676/courses/linux-security.php7 -X POST -d 'FUZZ=key' -H 'Content-Type: application/x-www-form-urlencoded'

This command yielded an overwhelming amount of results that needed to be filtered out by file size. I filtered the results with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u \http://faculty.academy.htb:46676/courses/linux-security.php7 -X POST -d 'FUZZ=key' -H 'Content-Type: application/x-www-form-urlencoded' -fs 774

This revealed a second parameter of 'username'. Submitting both parameters 'user' and 'username' satisfied the requisites of the objective.

![[Pasted image 20240325152753.png]]

#### Fuzzing Values

The last objective of the exercise is to fuzz scan for values associated with these parameters that will be accepted. Since these are usernames, I knew that I would need to use an appropriate wordlist for this.

I decided to go with the wordlist in the following directory:

>/opt/useful/SecLists/Usernames/top-usernames-shortlist.txt

## NOTE 

***At this point the lease time of the server I was using expired, so the PORT changed from 46676 to 41440.***

I used this wordlist in the following command to fuzz for accepted username values:

>ffuf -w /opt/useful/SecLists/Usernames/top-usernames-shortlist.txt:FUZZ -u \http://faculty.academy.htb:41440/courses/linux-security.php7 -X POST -d 'username=FUZZ' -H 'Content-Type: application/x-www-form-urlencoded'

Which output the following results:

![[Pasted image 20240325154426.png]]

When a filter was applied to these results, no valid results were returned.

I then attempted to use the 'root' username to try to access the page:

>curl \http://faculty.academy.htb:41440/courses/linux-security.php7 -X POST -d 'username=root' -H 'Content-Type: application/x-www-form-urlencoded'

This did not grant access or return a flag. I tried some more usernames like 'admin', 'administrator', 'vagrant', and 'puppet', yet none of these granted access. I became suspicious of the filtering anomaly and decided to use a different username wordlist from the SecLists directory.

I decided to use a larger wordlist of usernames:

>/opt/useful/SecLists/Usernames/xato-net-10-million-usernames.txt

I once again ran the following modified command to implement the new wordlist and enumerate possible usernames:

>ffuf -w /opt/useful/SecLists/Usernames/xato-net-10-million-usernames.txt:FUZZ -u \http://faculty.academy.htb:41440/courses/linux-security.php7 -X POST -d 'username=FUZZ' -H 'Content-Type: application/x-www-form-urlencoded'

This command yielded an overwhelming amount of results that needed to be filtered out by file size. I filtered the results with the following command:

>ffuf -w /opt/useful/SecLists/Usernames/xato-net-10-million-usernames.txt:FUZZ -u \http://faculty.academy.htb:41440/courses/linux-security.php7 -X POST -d 'username=FUZZ' -H 'Content-Type: application/x-www-form-urlencoded' -fs 781

This yielded only two username results instead of many: 'harry', and 'Harry'.

![[Pasted image 20240325160649.png]]

I then curled the username harry with the following command:

>curl \http://faculty.academy.htb:41440/courses/linux-security.php7 -X POST -d 'username=harry' -H 'Content-Type: application/x-www-form-urlencoded'

This command yielded the flag in the POST response header as shown below:

![[Pasted image 20240325160915.png]]

This flag satisfied the requisites for the final objective, leading to completion of the module after about 5 hours of diligent efforts.

### Summary

