# Python Libraries

Modules are Python files that contain classes and functions. Modules are a convenient way for people to create and share code blocks for different purposes.

A Library is a set of modules that can be imported into our program. 

#### Dir(datetime)

We can import the default Python library 'datetime' and examine it's contents to see the functions and methods available within it:

>import datetime
>dir(datetime)

Output:
>\['MAXYEAR', 'MINYEAR', '\_\_builtins__', '\_\_cached__', '\_\_doc__', '\_\_file__', '\_\_loader__', '\_\_name__', '\_\_package__', '\_\_spec__', 'date', 'datetime', 'datetime_CAPI', 'sys', 'time', 'timedelta', 'timezone', 'tzinfo']

An example of one of these imported functions in use:

>import datetime
>
>
>now = datetime.datetime.now()
>print(now)    # prints: 2024-02-28 11:53:45

A less cluttered method of importing and calling this function and method follows:

>from datetime import datetime as dt
>
>
>print(dt.now())

Please note that there are two newlines between the import line can the rest of the code, this is defined as standard in the PEP8 guide on style.