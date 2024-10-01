# Filtering

FFUF will allow us to match or filter for indicated HTTP codes, response sizes, or word amount. This information is provided in the help menu:

>ffuf -h

While FFUF allows us to match cases, this is not helpful since we don't have suggestions for what the Vhosts might be named. Instead we will need to filter by file size since we know that incorrect results response size is 900. This can be filtered out with the -fs flag.

Use the following command to scan for vhosts while filtering out incorrect responses by size:

>ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u \http://academy.htb:PORT/ -H 'Host: FUZZ.academy.htb' -fs 900

If it hasn't been done already, add 'admin.academy.htb' to 'etc/hosts' with the following command:

>sudo sh -c 'echo "SERVER_IP admin.academy.htb" >> /etc/hosts'