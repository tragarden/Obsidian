# Web Fuzzing

Fuzzing is a technique that submits types of user inputs to an indicated interface in order to study how the interface reacts to requests. An example of this is submitting special characters into input fields in search of SQL vulnerabilities. Similarly, very long strings could be submitted in order to determine the buffer overflow that occurs during code breaks.

### Wordlists

FFUF is a tool that automates the fuzzing experience by implementing a wordlist for testing a URL. This is a way of exploiting the path portion of a domain name by inserting keywords that may take us to hidden pages. FFUF will inject common path keywords like '/login', '/admin', '/employees', etc. in order to find pages that aren't found within the site navigation tools. This is similar to bruteforcing passwords via Dictionary Attacks.

#### Pwnbox

In the hackthebox site VM Pwnbox, you will see the entire repository of Seclists under the directory /opt/useful/SecLists. The most common wordlist we will use from this directory is 'directory-list-2.3' which comes in several formats and sizes.

For the following modules, you will use this command to find the wordlist:

>locate directory-list-2.3-small.txt

Which returns the directory:

>/opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt

If you observe this wordlist you will find that the beginning contains information about copyright comments. This can clutter our results and should be removed by including the -ic flag.

