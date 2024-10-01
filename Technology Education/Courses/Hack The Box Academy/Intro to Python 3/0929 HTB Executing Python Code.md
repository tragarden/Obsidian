# Executing Python Code

Two of the common methods for Python code execution include executing a .py file or running it within the Python Integrated Development Learning Environment ( #IDLE).

Running Python as a file is useful for developing scripts, and running it in the IDLE is useful for running small tests on a project.

Hello World welcome.py file:

>print("Hello Academy!")

This is the most basic line of code and prints the string "Hello Academy!" to the console output. 

Now that a file has been written, open up VIM and execute it in Python with the following command:

>vim welcome.py
>python3 welcome.py

### IDLE

We can run IDLE in the terminal by execting python binary with no provided arguments. If you submit a mathematical expression to IDLE, it will return the answer value in the console output. If you use variables to perform this math, nothing will be provided within the output.

To exit IDLE, type 'exit(0)'. The 0 is the return code for Python processes - 0 translates to 'OK' in python. Any number besides 0 will return an error.

To initialize the IDLE interface in the terminal, use the following command:

>python3

Now you can submit mathematical expressions and IDLE will respond with answers.

Enter the following code to exit IDLE:

>exit(0)

It should be noted that Python executes from top down. Any values you are interacting with on the current line must be defined there or above this line. Any values below this line will not be recognized by Python.

Create a variable that stores a string and then use the variable as an argument for the built-in print function:

>greeting = 'Hello again, Academy'
>print(greeting)

Try storing multiple variables and printing them with the following commands:

>a = 'HTB'
>b = 'Academy'
>print(a, b)

#### Shebang

We can include a shebang (#!) on the first line of the script paired with a path to cause the following commands and arguments to be executed when the program is called. This gives the script execution rights and allows it to be executed without entering 'python' at the beginning of our terminal session. The file name is passed as an argument.

Use a shebang and the file path provided to give execution rights to a file containing a print statement:

>\#!/usr/bin/env python3
>
>print("Hello Academy!")

Now use the following commands to grant appropriate permissions and execute the file:

>chmod +x welcome.py
>./welcome.py

This will print the string contained in the welcome.py file.