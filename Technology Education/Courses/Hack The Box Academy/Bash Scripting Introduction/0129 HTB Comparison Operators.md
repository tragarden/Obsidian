# Comparison Operators

Comparison Operators in bash are used to compare values. There are four types of comparison operators in bash:

- string
- integer
- file
- boolean

### String Operators

| Operator | Description                          |
| :------: | ------------------------------------ |
|    ==    | equal to                             |
|    !=    | not equal to                         |
|    <     | less than in ASCII alphabet order    |
|    >     | greater than in ASCII alphabet order |
|    -z    | if the string is empty / null        |
|    -n    | if the string is not null            |

Note that if we were to put the special variable ($1) in double quotes ("$1") this would be treated as a string and not a variable.

Note that the string comparison operators \< and \> only work within double square bracketing \[\[ \<likeThis> ]]

If you need to review the American Standard Code for Information Interchange ( #ASCII) for 7-bit character encoding, use the following command:

>man ascii

### Integer Operators

Integer operators are very straight forward in bash.

| Operator | Description              |
| :------: | ------------------------ |
|   -eq    | equal to                 |
|   -ne    | not equal to             |
|   -lt    | less than                |
|   -le    | less than or equal to    |
|   -gt    | greater than             |
|   -ge    | greater than or equal to |

### File Operators

File operators are useful for determining set permissions and file or directory content.

| Operator | Description                                     |
| :------: | ----------------------------------------------- |
|    -e    | if the file exists                              |
|    -f    | tests if it's a file                            |
|    -d    | tests for directory                             |
|    -L    | tests for symbolic link                         |
|    -N    | checks if the file was modified after last read |
|    -O    | if current user owns the file                   |
|    -G    | if the group ID matches current users           |
|    -s    | tests for file size greater than zero           |
|    -r    | tests for read permission                       |
|    -w    | tests for write permission                      |
|    -x    | tests for execute permission                    |

### Boolean Operators

Boolean values are true or false. Bash will allow you to compare string values with these boolean values within double square brackets \[\[ ]].

### Logical Operators

| Operator | Description             |
| -------- | ----------------------- |
| !        | logical negotiation NOT |
| &&       | logical AND             |
| \| \|    | logical OR              |

### Exercise Script

The following script is provided for the exercise questions at the end of the module:

>#!/bin/bash
>
>var="8dm7KsjU28B7v621Jls"
>value="ERmFRMVZ0U2paTlJYTkxDZz09Cg"
>
>for i in {1..40}
>do
>	var=$(echo $var | base64)
>	
>	#<----- If condition here:
>done

