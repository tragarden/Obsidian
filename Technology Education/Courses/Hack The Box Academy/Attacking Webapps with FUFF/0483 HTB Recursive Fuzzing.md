# Recursive Fuzzing

So far we have fuzzed directories and files. There may be many directories and  subdirectories with their each files, and fuzzing each directory for files manually can be quite time consuming and inefficient. We can automate this process through a method known as recursive fuzzing.

We can specify a depth of our recursive scan so that it will only scan through an indicated amount of directories. We do this by implementing the -recursion and -recursion-depth flags. 

A flag utilizing -recursion-depth 1 will only fuzz the first level of subdirectories under the indicated directories. We can specify extensions with the -e flag, an example would be -e .php.

We will likely need to use the -v flag to reveal the full URL addresses, otherwise it will be difficult to determine which .php files are within which directories.

We can use the following flag to recursively scan for directories and files that are within the first level of subdirectories with the following command:

>ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ -u \http://SERVER_IP:PORT/FUZZ -recursion -recursion-depth 1 -e .php -v

