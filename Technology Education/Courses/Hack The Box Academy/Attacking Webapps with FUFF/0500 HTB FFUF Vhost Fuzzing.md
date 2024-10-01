# Vhost Fuzzing

The difference between a sub-domain and a Vhost is like a sub-domain located on the same server with the same IP. This is akin to one IP serving multiple websites.

Vhosts may or may not have public DNS records.

In this case we will fuzz for Vhosts by fuzzing HTTP headers. We will specifically target the Host: header by using the -H flag.

Use the following command to fuzz the headers:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \http://academy.htb:PORT/ -H 'Host: FUZZ.academy.htb'

This should return 200 OK status' for every entry in the wordlist since we are changing the header while visiting the indicated domain.