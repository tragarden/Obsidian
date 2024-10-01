# Defining Functions

Before I define any functions, let's examine a password generator that takes a list value.

>wordlist = \['password', 'john', 'qwerty', 'admin']
>
>for word in wordlist:
>	counter = 0
>	while counter < 100:
>		print(f'{word}{counter}')
>		counter = counter + 1

This loop will iterate until it has processed all list element combinations.

Functions define code blocks that perform multiple actions and produce a range of values.

The first line of a function is called the signature.

To define a function in Python, we use the 'def' keyword:

>def f(x):
>	return 2 * x * 5 

This means that the function is named 'f' and takes parameter x. The def keyword defines the function and the return keyword returns a value to the output.  Note that the inner scope of the function must be indented.

If we call the function with an argument of 5, we get the following:

>f(5)

output: 50    # 2 * 5 * 5 

### Power of Function

Two asterisks ( ** ) in Python indicate 'to the power of' and allows for exponential expressions in Python.

To write the expresson as a function and then call it, observe the following code:

>def power_of(x, exponent):
>	return x ** exponent
>	
>power_of(4, 2)      # this will run the function but will not store any value
>eight = power_of(2, 3)    # the variable 'eight' is now equal to 2 to the power of 3

Although it may seem like there is no use for the first function call depicted here, it can actually be piped into other functions for use as seen in the following example:

>print('My favorite number is:')
>print(power_of(4, 2))

This would print the result of the nested function to the output.

### Named Parameters

So far we have used positional parameters. These parameters are defined by their position in a function definition. 

Named Parameters do not need to be in a specific order, but they must have the value explicitly assigned to the parameter they belong to.

Here is an example of Named Parameters in use:

>def print_sample_invitation(mother, father, child, teacher, event):
>
>	# Notice the use of multi-line format-string f''' text here''''
>	sample_text = f'''
>Dear {mother} and {father}.
>{teacher} and I would love to see you both as well as {child} at out {event} tomorrow evening. 
>
>Best regards,
>Principal G. Sturgis.
>'''
>	print(sample_text)
>	
>print_sample_invitation()

To call the function with parameters, see the following function call:

>print_sample_invitation(mother='Ashlee', father='Travis', child='Cornbread', teacher='Harry', event='Party')

