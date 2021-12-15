***
# Functions Best Practices 
***
***
# Function naming guidelines
* function names should be undercase seperated by underscores: ```my_func()```
* function names should typically contain verbs: ```insert_node```... ```find_name```
***
***
# Functions basic guidelines 
* functions should only do one thing
* functions should typically be less than 100 lines (some places even say less than 20 lines long)
***
***
# Arguments best practices
* a functions paramater list should be as short as possible
* bad:
```
def find_distance(x1,x2,x3,x4,x5,x6):
    # Code
```
* better:
```
def find_distance(point1, point2):
    # Code
```
***
*** 
# Multi-line arguments list
* it should have a hanging indent and should look something like this: 
```
def function_name(
       param1, param2, param3,
       param4, param5,
       param6):
    # Code
```
* notice the indentation if the params vs the code
* the paramas should be alligned vertically 
* the 4 space rule is optional for continuation lines
***
***
# Use "return" statements consistently
* this is bad:
```
def divide(x, y):
    if y != 0:
        return x / y
    else: 
        return
```
* also bad: 
```
def divide(x, y):
    if y != 0:
        return x / y
```
* this is better:
```
def divide(x, y):
    if y != 0:
        return x / y
    else: 
        return None
```
***
***
# Whitespaces around keyword arguments
* dont use spaces around an = sign when its used to indicate a key word argument, or when its used to indicate a default value
* good:
```
def sort(data, reversed=False):
    # Code 
```