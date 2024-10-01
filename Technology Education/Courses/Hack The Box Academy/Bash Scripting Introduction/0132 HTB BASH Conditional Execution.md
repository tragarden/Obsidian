# Conditional Execution


#### Shebang

A #shebang is at the top of every bash script and begins with "#!" denoting the path to the file that will be executed. Shebangs are not exclusive to bash and are using in other scripting languages like #Python and #Perl as well.

Shebang examples include:

>#!/bin/bash

>#!/usr/bin/env python

>#!/usr/bin/env perl

### Script.sh

>#!/bin/bash
>
># Check for given argument
>if \[ $# -eq 0 ]
>then
>	echo -e "You need to specify the target domain.\\n"
>	echo -e "Usage:"
>	echo -e "\\t$0 \<domain>"
>	exit 1
>else
>	domain=$1
>fi


In the above code:

- #!/bin/bash - this is the shebang
- if-else-fi - this is the conditional execution
- echo - this is the print statement
- $# / $0 / $1 - these are special variables
- domain - this is a variable

### If-Else-Fi

#If-Else statements are used to process conditional cases. Checking for conditions is possible using if-else conditionals and case statements. By default an if-else conditional can only use a single 'if' statement. 

#### If-Else Pseudocode

>if \[ the number of given arguments equals 0 ]
>then
>	print: "You need to specify the target domain."
>	print: "\<empty line>"
>	print: "Usage:"
>	print: "   \<name of the script> \<domain>"
>	Exit the script with an error
>else
>	The 'Domain' variable serves as the alias fro the given argument
>finish the if-condition

### If-Only

This case of the 'If' conditional only includes the 'if' part of the 'if-else' statement. This means "if something happens, then do this" and nothing else. This is the default implementation.

>#!/bin/bash
>
>value=$1
>
>if \[ $value -gt "10" ]
>then
>	echo "Given argument is greater than 10."
>fi

#### If-Only.sh - execution

The following command would return no output:

>bash if-only.sh 5

The following command would return the output "Given argument is greater than 10."

>bash if-only.sh 10

### If-Elif-Else

When elif or else is added to an if statement, it makes the program more dynamic and allows for more outcomes. The following code will print three different statements depending on the situation.

#### If-Elif-Else.sh

>#!/bin/bash
>
>value=$1
>
>if \[ value -gt "10" ]
>then
>	echo "Given argument is greater than 10."
>elif \[ $value -lt "10" ]
>then
>	echo "Given argument is less than 10."
>else
>	echo "Given argument is not a number."
>fi

#### If-Elif-Else.sh - execution

The following command would return the output "Given argument is greater than 10."

>bash if-elif-else.sh 12

The following command would return the output "Given argument is less than 10."

>bash if-elif-else.sh 4

The following command would return the output "Given argument is not a number."

>bash if-elif-else.sh okay

### Several Conditions

To extend upon our original script for this page, we will extend the functionality of it with the following additional conditions:

>#!/bin/bash
>
># Check for given argument
>if \[ $# -eq 0 ]
>then
>	echo -e "You need to specify the target domain.\\n"
>	echo -e "Usage:"
>	echo -e "\\t$0 \<domain>"
>	exit 1
>elif \[ $# -eq 1 ]
>then
>	domain=$1
>else
>	echo -e "Too many arguments given."
>	exit 1
>fi

This block of code will now respond with an error message if too many arguments are supplied.

### Exercise Script

The following code is used to perform an exercise in the module:

>#!/bin/bash
># Count the number of characters in a variable:
>#           echo $variable | wc -c
>
># Variable to encode
>var="nef892na9s1p9asn2aJs71nIsm"
>
>for counter in {1...40}
>do
>	var=$(echo $var | base64)
>done

### Objective

The objective is to write an if/then statement that will evaluate the content of the 35th iteration of the loop. We want it to print the total number of characters in this iteration.

I was quite confused about the exercise script and how it worked. This is supposed to be an intro to bash but there is very poor documentation related to this activity.

I found useful posts online that explained the content of this script and provided the answers.

>#!/bin/bash         this is the shebang
>
># count the number of characters in a variable with the following line
>#         echo $variable | wc -c
>
># Variable to encode
>var="nef892na9s1p9asn2aJs71nIsm"
>
>for counter in {1...40}    # this line is a loop that iterates 40 times
>do
>	# the following line evaluates what is in parentheses and then assigns it to var
>	var=$(echo $var | base64)     # this line converts var to base64 and reassigns it to var
>	if \[ $counter -eq 35 ]    # this conditional checks if the iteration is 35
>	then
>		echo "The number of characters in 35th iteration of var is: $(echo $var | wc -c)"
>		# The above echo pipes var output to wc -c which counts the characters.
>		# $(...) is command substitution, the shell executes the parentheses first.
>		# echo $(...) outputs the result into the print statement
>	fi
>done

This will return the value 1197735. There are this many characters total in the 35th iteration of this loop.

