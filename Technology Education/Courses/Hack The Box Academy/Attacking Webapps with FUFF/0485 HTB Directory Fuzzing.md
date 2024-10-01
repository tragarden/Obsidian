# Directory Fuzzing

Fuzz Faster U Fool ( #FFUF) is installed on the VM we will be using, but alternatively you can download it onto your own machine with the following command:

>apt install ffuf -y

Use the following command to see the help menu for ffuf:

>ffuf -h

### Fuzzing

Two options presented in the help menu are -w (wordlist) and -u (URL).

We can also indicate a wordlist we would like to work with and assign it to a keyword for easier use. Assign the wordlist to the FUZZ keyword with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ

Now we can supply a domain with the -u flag and apply the wordlist to the path variable with the FUZZ keyword. Do so with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://SERVER_IP:PORT/FUZZ

In the example shown, you will see that FFUF tested over 90,000 URLs in 10 seconds.  dire