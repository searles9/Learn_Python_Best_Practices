***
# Sequences Best Practices (list, tuples and dictionaries)
***
***
# Multi line constructs
* ex - good:
```
long_list = [
    1,2,3
    4,5,6
    ]
```
* this also works:
```
long_list = [
    1,2,3
    4,5,6
]
```
***
***
# Sequences as Truthy and Falsy values
* Non empty sequence = True
* Empty  = False ( set() is False)
* bad: ``` if len(my_list) > 0 :```
* good: ```if my_list``` ... if my_list has items in it it will evaluate to True and will run 
* if you want to run code if a list is empty do something like this... ```if not my_list```
***
***
# List comprehension and when to use it
* 