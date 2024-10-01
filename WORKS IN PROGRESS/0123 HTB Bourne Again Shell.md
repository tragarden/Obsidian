# Bourne Again Shell

Bourne Again Shell ( #BASH) is a scripting language for #Unix based operating systems ( #OS). It is also available for #Microsoft products since the advent of #Windows Subsystem for #Linux since 2019. A key distinction between a scripting language and a programming language is that programming languages must compile code while scripts can be executed instantly.

The main functions of a scripting language include:

- Input
- Output
- Arguments
- Variables
- Arrays
- Conditional Execution
- Arithmetic
- Loops
- Comparison Operators
- Functions

Scripts do not create processors, they are parsed into an interpreter that executes the script. When executing a script in BASH, we must specify the interpreter and designated script as seen in the varying syntax of the following commands:

>bash script.sh \<optional arguments>

>sh script.sh \<optional arguments>

>./script.sh \<optional arguments>

In the following command we will execute a script within the following domain:

>./CIDR.sh inlanefreight.com

#### Shebang

A #shebang is at the top of every bash script and begins with "#!" denoting the path to the interpreter that is being used. Shebangs are not exclusive to bash and are using in other scripting languages like #Python and #Perl as well.

Shebang examples include:

>#!/bin/bash

>#!/usr/bin/env python

>#!/usr/bin/env perl

### If-Else-Fi

#If-Else statements are used to process conditional cases. Checking for conditions is possible using if-else conditionals and case statements. By default an if-else conditional can only use a single 'if' statement. 

### If-Only

This case of the 'If' conditional only includes the 'if' part of the 'if-else' statement. This means "if something happens, then do this" and nothing else.