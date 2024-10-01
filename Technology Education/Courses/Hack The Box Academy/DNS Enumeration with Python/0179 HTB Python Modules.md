# Python Project Modules

For this project we will need to perform a zone transfer, which means we will need to use appropriate classes and functions to interact with DNS servers.

The module 'dnspython' will allow us to interact with DNS servers in a meaningful way.

The module 'IPython' will provide useful extensions like auto-completion and displaying various options for classes and modules within an interactive Python shell.

### Help Command

When using IPython, we will need to examine the modules that come with it and then use the help command to determine how to use them.

You can reveal a list of the ipython modules using the following command:

>ipython

Once you have displayed the list of modules, use the help() command to read about them:

>help(dz.from_xfr)

This will display the documentation for the dz.from_xfr function.

#### Class Import

Two classes we will need are dns.query and dns.zone, which we will store under the variables dz and dq respectively.

Use to following code to import these classes as their designated use names:

>import dns.zone as dz
>import dns.query as dq

Note that instead of calling the function dns.query.xfr(), we will be calling it under it's newly assigned name dq.xfr().

Call the documentation for the dq.xfr() function:

>help(dq.xfr)

When we examine the documentation, it is evident that all parameters are already assigned a value except for 'where' and 'zone'. This indicates that when we supply parameters to the function, 'where' and 'zone' will be those parameters.

Alternatively, you could execute the function and this would reveal the parameters that are missing as well.

In the case of this function, 'where' is the DNS server and 'zone' is the domain.

The following comment explains the syntax of this function:

># axfr = dz.from_xfr(dq.xfr(nameserver, domain))

### DNS Requests

The simplest way to resolve our DNS requests using a specific server is to use the dns.resolver class. The .resolver class allows us to indicate a DNS server to use. This can be done automatically, but sometimes sites use a third-party DNS server that does not allow for tests to be performed on them. Specifying these servers manually via the command line is a better method than hard-coding them. We can do this by importing the 'argparse' module.

Adding these two classes into our import code:

>import dns.zone as dz
>import dns.query as dq
>import dns.resolver as dr
>import argparse
>
># axfr = dz.from_xfr(dq.xfr(nameserver, domain))
>
># NS = dr.Resolver()
># NS.nameservers = \['ns1', 'ns2']

Now we can search the NS records for the given domain. Instead of using the dig tool, use the Python modules:

>python3
>import dns.resolver
>
>nameservers = dns.resolver.query('inlanefreight.com', 'NS')
>for ns in nameservers:
>	print('NS:', ns)
>	
>NS: ns1.inlanefreight.com.
>NS: ns2.inlanefreight.com.

In other words, we have submitted the following information:

>Domain = 'inlanefreight.com'
>DNS Servers = \['ns1.inlanefreight.com', 'ns2.inlanefreight.com']

### DNS-AXFR.py

Now that we have broken down the process of assembling the code, we can combine everything we've written so far into a .py file:

>#!/usr/bin/env python3
>
># Dependencies:
># python3-dnspython
>
># Used Modules:
>import dns.zone as dz
>import dns.query as dq
>import dns.resolver as dr
>import argparse
>
># Initialize Resolver-Class from dns.resolver as 'NS'
>NS = dr.Resolver()
>
># Target Domain
>Domain = 'inlanefreight.com'
>
># Set the Nameservers that will be used
>NS.nameservers = \['ns1.inlanefreight.com', 'ns2.inlanefreight.com']
>
># List of found subdomains
>Subdomains = \[]

