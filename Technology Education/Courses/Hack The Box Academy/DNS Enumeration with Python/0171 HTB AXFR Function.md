# AXFR Python Function

The best practices suggested via PEP8 is to separate each individual process and build single functions for each one to facilitate easier debugging and clearer interpretation of the program.

We want to perform the following processes:

1. Create a function that performs a zone transfer with the parameters Domain and DNS server.
2. If the zone transfer is successful, display the subdomains and store them in a list.
3. If there is an error, inform us of the error that occurred.

### Functions

Functions should use the fewest amount of arguments possible - in our case, we will stick to three or less arguments. This will reduce the likelihood of errors. The arguments we will use for zone transfer are 'domain' and 'name server'. 

This is the full code we have constructed up to this point:

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

#### Pseudocode for Zone Transfer

The following is the pseudocode for performing the Zone Transfer:

># Define the AXFR Function
>def AXFR(domain, nameserver)
>
>	# try zone transfer for given arguments
>	# perform zone transfer
>	# if successful
>	# add all found subdomains to global subdomain list
>	# if zone transfer fails
>	
># Main
>if \_\_name\_\_ == '\_\_main\_\_'
>
>	# for each nameserver
>	# try AXFR
>	# print results
>	# print each subdomain

#### Try-Except

When code is syntactically correct, it can still experience errors during execution - these errors are known as exceptions.

A try statement can contain multiple except blocks to handle different exceptions with specific actions. At most, a single except block will be executed.

#### Pseudocode for Try-Except

># List of found subdomains
>Subdomains = \[]
>
># Define the AXFR Function
>def AXFR(domain, nameserver)
>
>	# try zone transfer for given arguments
>	try:
>		
>		# perform zone transfer
>		axfr = dz.from_xfr(dq.xfr(nameserver, domain))
>		
>		# if zone transfer successful
>		# add found subdomains to global subdomain list
>		
>	# if zone transfer fails
>	except Exception as error:
>		print(error)
>		pass

### If-Else

There will be if-else statements implemented to achieve what we need to do. This will be designed so that only one value or argument is assessed at a time.

### DNS-AXFR.py - If-else

># List of found subdomains
>Subdomains = \[]
>
># Define the AXFR Function
>def AXFR(domain, nameserver)
>
>	# try zone transfer for given arguments
>	try:
>		
>		# perform zone transfer
>		axfr = dz.from_xfr(dq.xfr(nameserver, domain))
>		
>		# if zone transfer successful
>		if axfr:
>			print('\[\*] Successful Zone Transfer from {}'.format(nameserver))
>		
>		# add found subdomains to global subdomain list
>		
>	# if zone transfer fails
>	except Exception as error:
>		print(error)
>		pass

### For Loop

Now we can design and implement a For Loop to add any discovered subdomains to the global subdomain list. This is done by appending each record to the predefined subdomains list. Please note that keeping For Loops simple is a good idea.

># List of found subdomains
>Subdomains = \[]
>
># Define the AXFR Function
>def AXFR(domain, nameserver)
>
>	# try zone transfer for given arguments
>	try:
>		
>		# perform zone transfer
>		axfr = dz.from_xfr(dq.xfr(nameserver, domain))
>		
>		# if zone transfer successful
>		if axfr:
>			print('\[\*] Successful Zone Transfer from {}'.format(nameserver))
>		
>		# add found subdomains to global subdomain list
>			for record in axfr:
>				Subdomains.append('{}.{}'.format(record.to_text(), domain))
>		
>	# if zone transfer fails
>	except Exception as error:
>		print(error)
>		pass