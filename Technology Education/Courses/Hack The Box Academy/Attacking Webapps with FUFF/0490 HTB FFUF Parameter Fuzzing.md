# Parameter Fuzzing

After fuzzing the domain admin.academy.htb, the URL \http://admin.academy.htb:PORT/admin/admin.php will be revealed. If this is entered into the browser however, it will not allow you to access the flag on the page. This means that some method of authentication is happening. 

It can be deduced that there are no credentials or cookies involved, so it is possible that a key is being passed to the page as a parameter via GET or POST requests via HTTP. Fuzzing for parameters can reveal publicly accessible parameters.

### GET

The GET request parameters are passed to the server in the URL, typically after the ? as shown in the following example:

>\http://admin.academy.htb:PORT/admin/admin.php?param1=key.

There is an appropriate wordlist in our directory as follows:

>/opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt

We can use the following command to fuzz parameters with this list and filter results:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u \http://admin.academy.htb:PORT/admin/admin.php?FUZZ=key -fs xxx

The hit that is returned can be input as a URL, but the returned page is deprecated. 

### POST HTB #0508

POST requests are not included within a URL and must be passed within the data field in the HTTP request. 

We can fuzz the data field of an HTTP request with the -d flag and the -X POST flag.

POST data content-type must be 'application/x-www-form-urlencoded'. This can be set in FFUF with the following flag:

>-H 'Content-Type: application/x-www-form-urlencoded'

We can use a similar command as the GET method earlier, we will just place the FUZZ keyword after the -d flag:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u \http://admin.academy.htb:PORT/admin/admin.php -X POST -d 'FUZZ=key' -H 'Content-Type: application/x-www-form-urlencoded' -fs xxx

In our current module, this will return the 'user' parameter and the 'id' parameter.

Send a POST request that uses the 'id' parameter with the following curl command:

>curl \http://admin.academy.htb:PORT/admin/admin.php -X POST -d 'id=key' -H 'Content-Type: application/x-www-form-urlencoded'

This will return the message 'Invalid ID!'

