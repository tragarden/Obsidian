### Overview

I am writing a Python algorithm that opens files and parses their contents. This algorithm uses a variety of functions, methods, keywords, parameters, arguments, and variables to create a function that takes two arguments to augment a list of existing IP addresses based on a list of IP addresses that should be removed.

### Scenario

I am working for a health care company that needs a file to be regularly updated. This file is a list of employees that are able to access restricted content that contains Sensitive Personally Identifiable Information ( SPII ) such as patient data and employee data. 

Employees are restricted from accessing this data based on their IP addresses, and there is an allow list of approved IP addresses that is allowed to access this content via the organization's restricted subnetwork. Conversely there is a remove list that identifies previously approved employee IPs that should be removed from the allow list.

I will be creating a Python algorithm that checks the allow list for any IP addresses that should be removed by citing the data within the remove list, then identifies and removes these IPs from the allow list.

## Project

I need to create an algorithm to parse file contents, read them, evaluate these contents using conditional statements, write to them, and print results. In this documentation, functions, methods, and terminology are indicated with *italics* and variables are indicated in **bold**.

#### Opening allow_list.txt

To begin this process, I assigned the file name 'allow_list.txt' as *string data* to a *global variable* called **import_file**. 

>import_file = "allow_list.txt"

I then assigned the *list data* of restricted IP addresses to a *global variable* called **remove_list**. 

>remove_list = \["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

Now that these variables are available, I used the *open()* function to read the .txt file using the **import_file** variable as the first parameter and the *r* parameter to indicate that I wanted this file to be read. 

I then stored this information to the variable **file** using the *as* keyword:

>with open(import_file, 'r') as file:

By using the *with* keyword, I was able to open and close the file with less lines of code for increased readability.

#### Reading allow_list.txt

Now that the allow_list.txt file is stored as **file** via the *open()* function, I can now use indentation and the *.read()* method on the variable **file** to read it as string data. 

I stored the resulting string in the variable **ip_addresses**.

> 	 ip_addresses = file.read()

I am now able to call the **print()** function to see this variable in the output to ensure that the contents of the file are presented as string data:

>print(ip_addresses)

My code thus far is working and is as follows:

>import_file = "allow_list.txt"
>remove_list = \["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
>
>with open(import_file, 'r') as file:
> 	 ip_addresses = file.read()
>print(ip_addresses)

![[global_variables.png]]

After examining the output from my Notebook entry, it is evident that the four IP addresses within the list data variable **remove_list** are still included within the allow_list.txt file. 

#### Converting ip_addresses to a List

Now that I have opened and read the file and viewed it's contents as a string in the output, I want to convert this string data into list data using the **.split()** method. This will allow me to remove the IP addresses within **remove_list** from the **ip_addresses** variable that holds allow_list.txt as string data.

To convert **ip_addresses** to list format, I used the *.split()* method.

>ip_addresses = ip_addresses.split()

To ensure that this method properly converted the data, I called the *print()* function with the argument **ip_addresses** to confirm via output.

>print(ip_addresses)

![[split_method.png]]

This depicted the content within **ip_addresses** as list data containing 17 IP address elements.
#### Iterating through ip_addresses

Now that **ip_addresses** is converted to list data, I constructed a *for loop* that iterated through the items within the list. I used the *loop variable* **element** to describe the list elements within **ip_addresses**. The *in* keyword indicates that I am evaluating each **element** in sequence within **ip_addresses** with the following statement:

>for element in ip_addresses:

I then called a *print()* function within the loop using **ip_addresses** as an argument.

>print(ip_addresses)

The following output shows the successful results of the iterating process:

![[for_loop.png]]

#### Remove remove_list Addresses from ip_addresses

In order to remove the designated IP addresses within **remove_list** from **ip_addresses**, I needed to create an indented *conditional if* statement that evaluates whether or not a given **element** is contained within **remove_list**. 

>	if element in remove_list:

After establishing the *conditional* statement, I used the *.remove()* method with the *argument* **element** applied to the **ip_addresses** variable with appropriate indentations. I can use the *.remove()* method because it is known there are no repeated elements in the **remove_list** list.

>		ip_addresses.remove(element)

To check the status of the algorithm, I called the *print()* function with the argument **ip_addresses**.

>print(ip_addresses)

![[remove_elements.png]]

In the output you can see that there are 13 IP address elements instead of the 17 elements depicted previously.

#### Update allow_list.txt

Now that I know the *elements* from **remove_list** were successfully removed from **ip_addresses**, the allow_list.txt file needs to be updated with the newly generated content. 

In order to do this, the list data from **ip_addresses** must be converted back into string data via the *.join()* method.

The *.join()* method will be applied to the string "\\n" to separate the strings in the original file by placing each one on a new line. This will be stored in the **ip_addresses** variable. 

>ip_addresses = "\\n".join(ip_addresses)

I then wrote this newly modified **ip_addresses** to the **file** variable using the *.write()* method with appropriate indentation. 

>	file.write(ip_addresses)

![[join_method.png]]

#### Reading the Update

I have not yet seen the contents of the rewritten allow_list.txt file. In order to do this, I will need to open the file again via the *open()* function with the parameters **import_file** and 'r' while storing this string content 'as' **file**.

>with open(import_file, 'r') as file:

Next I will use the *.read()* method applied to **file** to read this content and store it within the variable **text** with appropriate indentation.

>	text = file.read()

To confirm the contents of the file, I called a *print()* function with the *argument* **text**.

>print(text)

![[read_method.png]]

#### Defining a Function

Now that I have confirmed that the algorithm works, I will store it within a *function* that can easily be called and supplied with appropriate *arguments*. I will use the *def* keyword to define a *function* named **update_file** that accepts the parameters **import_file** and **remove_list**. 

>def update_file(import_file, remove_list):

Within the function body, all code except for the global variables **import_file** and **remove_list**, as well as the final *open()* function and *.read()* method will be included.

The following code will demonstrate the function definition, the body containing the rewriting algorithm, a function call for **update_file** with supplied example arguments, and lastly lines to open, read, and print the document contents.

>def update_file(import_file, remove_list):
>	with open(import_file, "r") as file:
> 	    ip_addresses = file.read()
>	ip_addresses = ip_addresses.split()
>	for element in ip_addresses:
>		if element in remove_list:
>			ip_addresses.remove(element)
>	ip_addresses = " ".join(ip_addresses) 
>	with open(import_file, "w") as file:
>		file.write(ip_addresses)
> 
>update_file('allow_list.txt', ["192.168.25.60", "192.168.140.81", "192.168.203.198"])
>	text = file.read()
>print(text)

![[complete_function.png]]

### Summary

I created a function that processes an algorithm that identifies IP Addresses from a variable remove_list and removes these elements from a file allow_list.txt that contains approved IP addresses. I did so by opening the file, converting it to a readable string, converting this string to a list, and storing this list in  a variable ip_addresses. 

I then iterated through the variable ip_addresses using a for loop that contained a conditional that evaluated elements of variable remove_list. 

I then implemented the .remove() method to remove the indicated elements from the list data in variable ip_addresses.

Next I used the .join() method to convert the modified variable ip_addresses into string data so the contents could be written to allow_list.txt via the .write() method. 

Finally allow_list.txt contents could be read, verifying successful implementation of the function and algorithm. 