***
# Operators Best Practices
***
***
# Parentheses in conditions and expressions
* parentheses have the highest priority
* Good: ```price + (price * tax_perc) - discount```
* too many parentheses hurts readability
***
***
# Comparison operators chaining
* ```a < b < c``` is better than ```if a < b and b < c ```
* ```x < y <= z```
* ``` if 18 < age < 45:```
* if the first portion is false, then the second portion is not evaluated
***
***
# The 'is' operator
* comparison to singletons like None should always be done with is or is not, never the equality operators 
* this is bad: ```if var == None:```
* this is what you should do... ```if var is None:```
* ```is``` compares the identity of two objects
* ```==``` compares the value of two objects
* identity != value
* is checks if the objects are the same in memory 
* singleton means only one instance can be created in the program
```
a = [1,2,3]
b = [1,2,3]

a == b
# this is true...value

a is b
# this is false , while the same values, they are not the same
# objects in memory ...identity
```
* there can only be one None object in memory 
```
None is None 
# True because only 1 None object can exists in memory
```
***
***
# is not vs not ... is
* it is reccomended to us ```is not``` instead of ```not is```
* both are functionally identical but ```is not``` is more readable
* bad: ```if not var is None```
* good: ```if var is not None:```
***
***
# Truthy and Falsy values
* you should not compare boolean values to True or False using ==
* bad: ```if is_valid == True:```
* very bad: ```if is_valid is True:```
* good: ```if is_valid:```
* False, None, 0 values, "", [], (), {}, set(), range(0) all evaluate to false by default
* dont use ```if x``` when you really mean ```if x is not none``` (explicit is better than implicit)
```
nums_list = [1, 2, 3]
     
if nums_list:
    print("Truthy = Not Empty")
else:
    print("Falsy = Empty")
```
***
***
