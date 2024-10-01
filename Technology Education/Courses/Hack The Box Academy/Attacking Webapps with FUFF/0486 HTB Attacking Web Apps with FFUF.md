# Attacking Web Apps

Now that we have successfully fuzzed directories within the URL and found two operational pages, we can continue to discover more pages this way once we determine if the site uses .html, .aspx, .php, or other extensions.

We can determine the server type via HTTP response headers and their related extensions. Apache servers typically use .php while IIS servers typically use .asp or .aspx. We can use ffuf to fuzz the extensions in a way that is similar to how we fuzzed the directories. This can be done by placing the FUZZ keyword where the site extension would be. We can do this with the web-extensions.txt wordlist.

Use the following command to fuzz the extensions for the site:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/web-extensions.txt:FUZZ -u \http://SERVER_IP:PORT/blog/indexFUZZ

Now we can use the wordlist directory-list-2.3-small.txt to fuzz for pages:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://SERVER_IP:PORT/blog/FUZZ.php

