The following is taken from module #0499 about DNS records and adding them to local domain files.

# #0499 DNS Records

If we try to visit the site academy.htb, we will find that we cannot connect to this site because this is a private website locally hosted by HTB. This isn't located within the /etc/hosts directory file, and it isn't in the DNS server because it is a privately hosted site. The only way we can access it is if we add it to our /etc/hosts directory file which is acting as a local cache for local sites.

We can add this domain to the /etc/hosts file with the following command:

>sudo sh -c 'echo "SERVER_IP academy.htb" >> /etc/hosts'

This will take us to the same page that is associated with \http://SERVER_IP:PORT - they are the same domain. If we use the path /blog/index.php, it will take us to a page we have previously visited.

Since our last fuzzing results didn't reveal any admin pages, we can now try to find subdomains under the '\*.academy.htb' domain.

# #0488 Sub-Domain Fuzzing

The subdomain of the following URL '\http://photos.google.com' is 'photos', and we can scan for these by using the wildcard \* in the format of "\http://\*.google.com"

We can find the wordlist for common subdomain names in the /opt/useful/SecLists/Discovery/DNS/ directory under the filename 'subdomains-top1million-5000.txt'.

We will use the target \inlanefreight.com in the example given with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \https://FUZZ.inlanefreight.com/

Now do the same for the academy.htb domain with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \https://FUZZ.academy.htb/

This command will yield no sub-domains, but that does not mean there are no sub-domains because we are only scanning for publicly listed domains and the domains in this case are private. Since this is the case, they are not within the /etc/hosts file and thus will not be in the output.

