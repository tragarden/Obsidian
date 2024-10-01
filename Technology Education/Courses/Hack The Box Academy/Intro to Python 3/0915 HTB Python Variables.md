# Python Variables

Mathematics and Programming have some shared elements: they both heavily rely on variables, constants, and functions.

A variable is a way that data is stored in memory. 

Some example variables in the following Python file:

>advice = 'Don't panic'
>ultimate_answer = 42
>potential_question = 6 * 7 
>confident = True
>something_false = False
>problems = None
># Oh, and by the way, this is a comment. It is indicated by the '#'.

##### Strings

The first variable in the above file is a string. Strings can be written within single or double quotes. If your string contains apostrophes, it is advised that you use double quotes in these cases. 

##### Integers

The second variable is an integer. Integers are whole numbers.

##### Booleans

A Boolean value is a binary or Truth value, which is indicated by either true and false or 1 and 0.

'None' is a value that represents nothingness, and in other languages this is referred to as 'null'. This is used to define variables that have not yet been assigned any value, allowing us to pass either some data or none to avoid errors. It is also used to return if 'none of something' was found.

##### Comments

Comments are ignored by the Python interpreter and are provided for the humans reading the program. It is used to create developer notes and descriptions in the program without affecting the code.

#### Practice

Store some integer calculations in variables in the following python file:

>add = 10 + 10
>sub = 20 -10
>multi = 5 * 5
>div = 10 / 5
>
>print(add, sub, multi, div)

This will print the results of the four mathematical expressions defined as global variables.

Now these variables can be further manipulated in mathematical expressions in the following continuation of our existing file:

># continued:
># (20 * 10 ) -  ( 25 * 2 )
>result = (add * sub) - (multi * div) 
>print('Result: ', result)

This file would print the result of the mathematical expression that utilized the variables we created. The comment shows the literal math that is represented by the variables.

When using IDLE, it will store the most recent expression calculation to the variable '\_'. Using the underscore character recalls the last calculated expression.

An example of the underscore (\_) variable is in the following IDLE commands:

>>>38 + 4
>42
>>>50 - \_
> 8

Note that this underscore variable ONLY works within IDLE. In regular Python file execution, this variable is usually only used to hold values we do not have high concern for.

### Style Guides

You should apply the snake_case naming convention when writing in Python. This means using all lowercase letters with underscores for the space between them. There are style guides, such as #PEP8 that should be followed when you are writing code that will be seen by others. This guide improves debugging, modification, and extensions of python code.
