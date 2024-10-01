# Arguments Variables and Arrays

### Arguments

Bash scripts allow us to pass up to 9 arguments without assigning them to variables. The first argument $0 is reserved for the script itself, but the other $1-$9 are available for our use. The dollar sign ( $ ) is used to indicate the position that the variable will be placed at. 

| Arguments:   | ./script.sh | ARG1 | ARG2 | ARG3 | ARG4 | ARG5 | ... | ARG9 |
| ------------ |:-----------:|:----:|:----:|:----:|:----:|:----:|:---:|:----:|
| Assignments: |     $0      |  $1  |  $2  |  $3  |  $4  |  $5  | ... |      |

These variables are known as special variables and indicate the arguments in a relational way.

Let's return to the script developed in the previous exercise:

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

#### Execution

If we wanted to execute the above script, cidr.sh, we would need to set execution privileges

To set execution privileges for the file, use the following command:

>chmod +x cidr.sh

To execute the file without providing arguments but while having execution privileges:

>./cidr.sh

To execute without having execution privileges:

>bash cidr.sh

### Special Variables

Bash provides various special variables that are identified with the Internal Field Separator ( #IFS). This is used to identify where one argument ends and another begins.


| IFS | Description                                                         |
| --- | ------------------------------------------------------------------- |
| $#  | holds the number of arguments passed to the script                  |
| $@  | retrieves the list of command-line arguments                        |
| $n  | represents the positional arguments $1-$9                           |
| $$  | the process ID of the currently running process                     |
| $?  | exit status of the script. 0 indicates success, 1 indicates failure |

### Variables

A dollar sign ( $ ) is used to allow the variable to be used in other code sections. If there is no $ used in assignment, it can only be used within that code block. 

Bash does NOT differentiate between data types like strings, integers, and booleans. All variable content is treated as a string.

It should also be noted that when defining a variable in bash, you CAN NOT put a space between the variable name, equals sign, and variable content.

For example:

>variable = "this is incorrect syntax"

Output: command not found: variable

No spaces is the correct syntax for variable definitions.

>variable="this is correct syntax"
>echo $variable

### Arrays

Arrays in bash are when several values are assigned to a single variable and are known as Arrays. Arrays make it possible to store and process and ordered sequence of data. Arrays use zero-indexing, meaning that the first index is recognized as zero ( 0 ). 

An array declaration looks like the following:

>#!/bin/bash
>
>names=(me you him them they her harry walter)
>
>echo ${domains\[0]}

If values within a declared array are placed within double or single quotes, this will treat all items separated by a space as a single value.

