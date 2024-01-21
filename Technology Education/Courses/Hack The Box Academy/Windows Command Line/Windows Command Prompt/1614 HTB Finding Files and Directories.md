# Finding Files and Directories

### Search Methods

#### where

The where command is used to locate a file and the output will show you the absolute path for the file in question.

If the file is not within the current working environment, you can use the where command recursively to look through all directories with the /R option. 

#### Wildcards

If you want to search for a file that you don't know the name of, you can use the wildcard ( * ) operator to search for file extension names. If you wanted to find all the executable files in a particular directory, you could use the following command:

>where /R C:\\Users\\student\\ \*.exe

This would return any executable file within the student directory.

#### find

The find command is used to search for detecting strings or their absence within a directory. If we wanted to find the word 'password' within a file, we could use the following command:

>find "password" "C:\\Users\\student\\not-passwords.txt"

- /V is used to search through files and find lines where the given string is NOT present.
- /N will assign line numbers to each result.
- /I will ignore case sensitivity in results.

For example if we wanted to identify all lines that DO NOT have a specific #IP address, we could use the following command:

>find /N /I /V "IP Address" example.txt

#### findstr

The findstr command is similar to the find command but works more like the #grep command in #Linux. This command is used to employ pattern matching, #regex values, wildcard searches, and more. Some people think of this tool as the successor to the find command. 

#### Compare

The comp command evaluates each byte of data and compares the results between two designated files. These differences are represented by decimal formatting unless otherwise specified with modifiers.

- /A will reveal the differences between the files in #ASCII format.
- /L will attach line numbers to each result. 

If we were to compare two files with the same content, we could use the following command:

>comp .\\file .\\file2

If they are the same, the output for this command will return "Files compare OK" indicating that they are the same. This is useful for determining if core files like executables and scripts have been modified.

If the files are different, the output will return the line "Compare error at OFFSET 2" with the resulting differences listed below this line..

#### FC

the FC command will show you the lines that are different AND the characters that are different within that line. FC has more user friendly output that is easier to read. This is a more robust tool than the compare command, so checking out the FC help menu with the following command is quite useful:

>fc.exe /?

This will reveal the list of switches that are available for this tool.

- /N - this switch will return #ASCII terms in the output with line numbers.

#### sort

The sort command is capable of receiving input from files or pipe and can be used with pipe operators like <, >, and |. 

- /O - this is used to sort our input by alphabetical order. 
- /unique - this switch will return only unique results and skip redundant findings.


# NOTE THAT AFTER SSH'ING INTO THE TARGET, YOU NEED TO TYPE 'CMD' TO OPEN THE COMMAND LINE ON THE TARGET HOST. ONLY THEN CAN YOU BEGIN USING THE WHERE COMMAND. GODDDDD.

### Related:

- [Hack The Box Academy](https://academy.hackthebox.com/ 'hack the box academy home page')
- [HTB Academy Finding Files and Directories](https://academy.hackthebox.com/module/167/section/1614 'HTB academy Windows finding files and directories guide')
- [012 Windows Command Line Tools](012%20Windows%20Command%20Line%20Tools.md)
- [012 Windows Network Command Line](012%20Windows%20Network%20Command%20Line.md)
- [013 Additional Windows Tools](013%20Additional%20Windows%20Tools.md)
- [015 Windows Settings](015%20Windows%20Settings.md)
- [031 Troubleshooting Windows](031%20Troubleshooting%20Windows.md)
- [018 File Systems](018%20File%20Systems.md)