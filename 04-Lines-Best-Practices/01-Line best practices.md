***
# Line Best Practices: Break, Length, and Blank Lines
***
***
# Line length limit
* PEP 8 reccomends that you should limit all lines to a maximum of ```79``` characters
* for flowing long block of text with fewer structural restrictions (docstrings or comments), the line lenght should be limited to ```72``` characters
* if your team needs to - It is ok to increase the line lenght limit to 99 characters provided that comments and docstrings are still wrapped at 72 characters
```
# Line length -> up to 99 characters
# Comments -> up to 72 characters
```
***
***
# Implied line continuation 
* what if a line is too long - then you can use implied line continuation (inside parentheses, brackets and braces)
* ```( )``` or ```{ }``` or ```[ ]```
* example line continuation:
```
if (<condition>
        and <condition2>
        and <condition3>):
    # code
```
```
def function_name(arg_one, arg_two,
                  arg_three, arg_four))
```
```
total = (price
            + tax
            - discount
            - coupouns)
```
```
print("This is",
         "a very long",
         "string!")
```
***
***
# Line breaks with backlashes
* you can break a line with back slashes 
* using line continuation ...ex ```()``` ... is implicit 
* using a backslash is explicit ```\```
* implicit line continuation is preferred over a backslash
* using a backslash is sometimes preferred when opening files though
```
with open('/path/to/file') as file1, \
    open('/path/to/file') as file2:
    # code
```
* ex:
```
total = price \
            + tax \
            - discount \
            - coupouns \ 
```
***
***
# Binary operators and line breaks
* a binary operator is an operation that combines two elements (operands) to produce another element 
* ```+ - * / // % **```
* and ```< <= > >= == !=```
* and ```and, or```
* it is reccomended to break the line before the binary operator
```
income = (gross_wages
          + taxable_intrest
          - ira_deduction)
```
* it is ok however to break before or after a binary operator, as long as the convention used is consistent in the code
***
***
# Avoid writing compound statements on a single line
* a compund statement is a statement that contains a group of other statments
* ``` if, while, for, try, with```
* comound statements on a single line are generally discouraged
* this would be discouraged...
```
# 1
if <condition>: do_this()

# 2
do_this() ; do_that() ; do_this()

# 3
x = 5 ; y = 2 ; z = 7

# 4
while <condition>: do_this()
``` 
***
***
# Blank lines in functions, methods and classes
* you should surround top-level function and class definitions with two blank lines - before and after
```
def a():
    #Code


def b():
    #Code


def a():
    #Code
```
* method definitions within a class should be surrounded by a single blank line
```
class Calculator:

    def __init__(self,price):
        self.price = price

    def add(self, a, b):
        return a + b 

```
* extra blank lines can be used (sparingly) to seperate groups of related functions
* you can use blank lines in functions (sparingly) to indicate logical sections
* blank lines may be omitted between a bunch of related one-liners
***
***