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
* use list comprehension when it makes your code easier to read
* syntax: ```[expression for item in iterable]```
* example:
```
pizza_letters = [letter.upper() for letter in "pizza"]
pizza_letters = [letter * 2 for letter in "pizza"]
pizza_letters = [letter for letter in "pizza"]
nums = [random.randint(1, 15) for i in range(250)]
theitems = [myfunction(var) for var in iterable]
the_nums = [i for i in range(50) if i % 2 == 0]
```
***
***
# Dictionary comprehension
* syntax: ```{key: value for elem in iterable }
* example:
```
my_dict = {i: i*2 for i in range(2, 8)}
my_dict = {item: round(price*1.2,3) for (item, price) in old_prices.items() }
```