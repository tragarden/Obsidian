# Main Function

The Main function contains the core components of the code. This should be concise and clear, while adding extra components later as needed.

If we initialize a Python program by calling a .py file and within this file we call the \_\_name\_\_ function, this will be assigned to the system variable \_\_main\_\_.

If we were to import this file into a different module however, this would get an identifier assigned to it according to that file name. The purpose of this is to use a Python file as a stand-alone program, makes elements of the file importable, and implements complex module tests.

So far, our current iteration of code before the Main function is as follows:

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

### DNS-AXFR.py Pseudocode

># Main
>if \_\_name\_\_ == '\_\_main\_\_'
>
>	# For each nameserver
>	# Try AXFR
>	# print results
>	# print each subdomain

### For Loop

Now we will incorporate a For Loop into the Main function to execute the AXFR function for each nameserver specified. The AXFR function requires two parameters: 'domain' and 'nameserver'.

We will then need to use a second For Loop that utilized if-else statements to output the discovered subdomains. If this list is not empty, it will be printed as standard output.

### DNS-AXFR.py For Loop

># Main
>if \_\_name\_\_ == '\_\_main\_\_'
>
>	# For each nameserver
>	for nameserver in NS.nameservers:
>	
>		# Try AXFR
>		AXFR(Domain, nameserver)
>		
>	# print results
>	if subdomains is not None:
>		print('-------- Found Subdomains:')
>		
>	# print each subdomain
>		for subdomain in Subdomains:
>			print('{}'.format(subdomain))
>			
>	else:
>		print('No subdomains found.')
>		exit()

### Completed Code

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
>
># Main
>if \_\_name\_\_ == '\_\_main\_\_'
>
>	# For each nameserver
>	for nameserver in NS.nameservers:
>	
>		# Try AXFR
>		AXFR(Domain, nameserver)
>		
>	# print results
>	if subdomains is not None:
>		print('-------- Found Subdomains:')
>		
>	# print each subdomain
>		for subdomain in Subdomains:
>			print('{}'.format(subdomain))
>			
>	else:
>		print('No subdomains found.')
>		exit()

### Make it Executable

Create a file named dns-axfr.py and place the code within it, then use the following commands to make the code executable:

>chmod +x dns-axfr.py
>./dns-axfr.py

