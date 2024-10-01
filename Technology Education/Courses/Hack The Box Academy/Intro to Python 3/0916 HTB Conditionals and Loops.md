# Conditional Statements and Loops

If, else, and elif statements are considered conditional statements in programming. 

#### If

The following code is an example of what a basic conditional statement looks like:

>happy = True
>
>if happy:
>	print("Happy and we know it!")
>else:
>	print("Not happy...")

It should be noted that indentation is required for Python code to execute correctly. The length of the indentations does not matter as long as they are consistent in size. HTB Academy and PEP8 use four spaces for Python indentation.

When examining the code above, it should be noted that the following statement is shorthand for a longer version:

>if happy:

is the shorthand notation for the expression:

>if happy == True:

#### Elif

The elif expression is used to make a multi-option if-else statement and is a form of nested 'if' statements.

An example of elif in use is in the following example:

>happy = 2
>
>if happy == 1:
>	print("Happy and we know it!")
>elif happy == 2:
>	print("Excited about it!")
>else:
>	print("Not happy...")

#### While 

While loops execute until their condition is no longer met. In other terms, this means that a True statement will run infinitely and a False statement will never run. If the statement remains true, this is known as an infinite loop and occurrences of this are problematic for programs. While loops typically depend on counters or breaks in order to prevent infinite loops. 

An example of a basic while loop is as follows:

>counter = 0
>
>while counter < 5:
>	print("f'Hello #{counter}')
>	counter = counter + 1

This code will begin at 0 and iterate 5 times until the counter reached 5 and ends the loop process by exceeding the conditional value <5. 

This loop also uses an f-string  or formatted string. Format strings allow us to populate a string with values that occur during runtime.

Format strings allow us to add thing into curly braces that will be determined as the prgram runs. Here are other examples.

>me = 'trag'
>greeting = f'Hello {me}!'

This would input the string assigned to the variable **me** into the string assigned the variable **greeting**.

#### For-each

A For-each loop or a For loop is one that iterates through items in a list in a sequential manner. Each element in the list is iterated in the order that they are written. 

Lists can be presented in two ways: single line or multi line. Single-line saves space while multi-line increases readability.

>groceries = \[ "onions", "carrots", "nuts"]

>groceries = [
>	"onions",       # index 0
>	"carrots",       # index 1
>	"nuts",           # index 2
>	"tools"           # index 3
>]

To call a certain element from a list, you use the variable name the list is assigned to and the index number included in square brackets after the variable name.

To call 'carrots' from the above example, you would type the following:

>groceries\[1]

You could also count the indexes backwards from the end of the list by incorporating a negative number in the indexing. 

An index of -1 would call the value from the end of the list:

>groceries\[-1]

This would return the 'tools' string element from the list.

#### Strings Index

An example of this indexing is demonstrated in the following code and output:

>var = "ABCDEF"
>print(var\[0], var\[1], var\[2], var\[3], var\[4], var\[5], )
>A B C D E F
>print(var\[-1], var\[-2], var\[-3], var\[-4], var\[-5], var\[-6])
>F E D C B A

#### Substrings

You can also take slices from strings using indexing:

>var = "ABCDEF"
>print(var\[:2])       # includes up to index 2
>AB
>print(var\[2:])     # ignores everything up to index 2
>CDEF
>print(var\[2:4])   # includes index 2 and anything between 2 and 4
>CD
>print(var\[-2:])   # includes up to negative index 2, or the last two characters
>FE

#### ForEach Loops

We can use the following code saved to groceries.py to say what we bought at the store:

>groceries = \[ "onions", "carrots", "nuts"]
>
>for food in groceries:
>	print(f'I bought some {food} today.')

If we execute our .py file in the command line as below, we get the following output:

>vim groceries.py
>python3 groceries.py

Output:

>I bought some onions today.
>I bought some carrots today.
>I bought some nuts today.

