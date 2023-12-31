# HTB Redeemer

This *Virtual Machine* ( #VM) demonstrates how to exploit the #Redis #in-memory #database type. This is a very **fast acting database that uses #RAM as an alternative to disk drives** or an #SSD.  The host server's RAM is used to listen for connections and supply the desired data.

*REmote DIctionary Server* ( #Redis) uses **open-source dictionary lookup** to function as a database, cache, and message broker. This uses #NoSQL #key-value pairs stored in a dictionary format in order to provide **extremely fast short-term data retrieval**.  

Redis will #cache and recently retrieved data for a set amount of time, which means that it is accessed extremely fast. **If Redis is queried and no relevant search data is within the cache, it will forward the client to slower databases** like #MySQL or #MongoDB. You can think of Redis as a great method of speeding up searches that are repeated frequently, like refreshing a page with a set of prices. Since these prices were likely previously queried and cached, we can quickly access them.

### Enumeration

#### Ping

We can **use a ping command** to ensure we are able to connect to the target host:

>ping 10.10.10.10

#### nmap

We can now **perform an #nmap scan** of the target host with the version flag -sV:

>sudo nmap -sV 10.10.10.10

This scan will reveal that **port 6379/tcp is open and the service Redis key-value store 5.0.7 is running**.

#### Redis

First we will need to **make sure Redis and it's #CLI tool are installed and updated**:

>sudo apt install redis-tools

*We can also connect with netcat as our listener*, but for the purpose of this lesson we will be using the redis-cli tool. 

Type the following to see the list of Redis commands:

>redis-cli --help

This will display commands and their appropriate formatting. After looking through the commands we can see that in order **to connect to a host, we use the -h flag** as presented below:

>redis-cli -h 10.10.10.10

We can now **use the 'info' command** to enumerate data from Redis:

>info

This will reveal quite a bit of information, but what we are seeking is at the bottom of the output titled "Keyspace". **Under the Keyspace header we can see that the assigned database is 0 (db0)** and that the **total amount of keys in this database is 4**. 

We can now **use the 'select' command to choose the database** named '0':

>select 0

Then we can **display ALL keys** within this database with the following command:

>keys *

This will reveal the names of the stored keys, presented below:

1. "temp"
2. "stor"
3. "numb"
4. "flag"

We can **use the following command to retrieve each #hash** for these keys:

>get temp
>get stor
>get numb
>get flag

The flag hash value will complete the module. 
