***
# Comments and Docstrings Best Practices
***
***
# Importance of comments
* Comments exists so you can help describe the logic of the code
* Comments should be high level, concise and meaningful 
* ```# Comment```
***
***
# Excessive commenting 
* avoid excessive commenting
* comments should not be a line by line description of the code
***
***
# Inline comments
* a comment that is inline on the same line as a statement 
* ```x = 5  # the comment```
* they should be seperated from the statment by 2 spaces, and the comment should be a space after the #
***
***
# Block comment
* a multi line comment 
```
# comment start
#
# comment stop
```
***
***
# Introduction to Docstrings
* docstrings are used to document an element of the code (module, function, method or class)
* the docstring is the first statement
* docstrings are connected to the element they describe, comments are not and comments are removed when the program is run
* __doc__ special attribute
* you should write a docstring for all public modules, unctions, classes and methods 
```
def foo():
"""This is a 
docstring
"""
    # code
```
***
***
# One line docstring
* you should always use triple quotes to define docstrings
* Example:
```
"""Return the sum of a and b"""
```
***
***
# Multi line docstrings
* example
```
def func(a,b):
    """Summary line.

    Elaborate description of the function.
    a -- desc of a (default 0.0)
    b -- desc of b (default 0.0)
    """
```
* example 2:
```
def func(a,b):
    """
    Summary line.

    Elaborate description of the function.
    a -- desc of a (default 0.0)
    b -- desc of b (default 0.0)
    """

```
* Items to describe for a function:
    * behavior 
    * arguments, optional arguments
    * return values
    * side effects
    * exceptions and restrictions
* Items to describe for a module
    * classes
    * exceptions
    * functions
    * any other object
    * one line summary of each
* Items to describe for a class
    * behavior
    * public methods
    * instance variables
    * docstrings for individual methods ... including __init__()

***
***
# Reading codstrings using __doc__
* ex:
```
def func(a,b):
    """
    docstring
    """

print(func.__doc__)
```
