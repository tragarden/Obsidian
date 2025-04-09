# SQL Operators

Logical Operators are used to manipulate multiple conditions simultaneously. The most commonly used operators are AND, OR, and NOT.

#### AND 

The AND operator requires two conditions and will return a binary response after evaluation of the command.  The AND operator will only return TRUE in cases where both indicated conditions are met.

Within the scope of MySQL, any non-zero value will return as true - 0 is considered false and 1 is considered true.

#### OR

The OR operator requires two conditions like the AND operator, but only one of these conditions needs to be met for the operator to return TRUE.

#### NOT

The NOT operator will toggle the current Boolean value to it's opposite state. 

#### Symbol Notation

The operators AND, OR, and NOT can be alternatively written as &&, ||, and !, respectively.

### Operator Precedence

You can think of this as PEMDAS, or order of operations, applied to the operators.

Here is the standard order of precedence established in order of highest priority to lowest:

- Division, Multiplication, and Modulus
- Addition and Subtraction
- Comparisons like less than, greater than, etc.
- NOT
- AND
- OR

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Introduction to SQL Operators](https://academy.hackthebox.com/module/33/section/192 "Intro to SQL Operators")