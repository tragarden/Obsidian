# Value Fuzzing

Now that we have usable parameters, we need to determine the value that would return the flag we are seeking. This method is similar to the parameter fuzzing methods, but we will instead use a custom wordlist.

### Custom Wordlist

We will implement a custom word list based on the idea that the ID parameter we used might use a numerical value for identifying users. Initially we can start with a number range from 0-1000 and increase this value to 0-10000 or greater if that isn't working.

We can use the following Bash command to create a list from 0-1000:

>for i in $(seq 1 1000); do echo $i >> ids.txt; done

To test this wordlist, use the following command:

>cat ids.txt

This should return a list of numbers from 0-1000.

### Fuzzing

The fuzzing method for values is similar to our methods for fuzzing parameters. We can use the custom wordlist we created in the following command:

>ffuf -w ids.txt:FUZZ -u \http://admin.academy.htb:PORT/admin/admin.php -X POST -d 'id=FUZZ' -H 'Content-Type: application/x-www-form-urlencoded' -fs xxx

Once we get a hit returned on this command, we can once again use curl to test this url:

>curl \http://admin.academy.htb:PORT/admin/admin.php -X POST -d 'id=key' -H 'Content-Type: application/x-www-form-urlencoded'

