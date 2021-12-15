***
# Write Clean Python Loops
***
***
# How to iterate over sequences using a for loop
* first aproach: 
```
for <var> in range(len(<sequence>)):
    # Code

for i in range(len(nums_list)):
    # Code
    print(nums_list[i])
```
* this is the better approach:
```
for var in sequence:
    # code
```
* iterating over dictionaries is a little different 
    * to iterate over the keys: ```<dict>.keys()```
    * to iterate over the values: ```<dict>.values()```
    * to iterate over the pairs:   ```<dict>.items()```
* example iterating over dictionaries: 
```
# keys
for key in my_dict.keys():
    print(key)

# value
for value in my_dict.values():
    print(value)

for key in my_dict:
    print(key)

# key and value
for key, values in my_dict.items():
    print(key, value)
```
***
***
# How to define multible loop variables
* to define and update to or more loop variables do something like this:
```
for var1, var2 in sequence:
    # Code
```
* the elements of the iterable must have the same number of variables that you define
```
# tuple lenght of 2 = 2 loop variables 

scores = [("Dan", 200), ("Donny", 45)]

for username, score in scores:
    print(username, score)
```
***
***
# Enumerate()
* this can be used to automatically keep track of a counter while iterating over an iterable 
* enumerate returns a tuple contaning a count which defaults to 0 and the values obtained from iterating over the iterable ```enumerate() -> clount + values```
```
x = [1,2,3]
enumerate(x) # returns an enumerate object

# the enumerate object looks like this (count, value):
# [(0,1),(1,2),(2,3)]

# to view the return object:
list(enumerate(x))
```
* to use the cound index use something like this:
```
x = [1,2,3]

for index, item in enumerate(x)
    print(item, "is index", index)
```
* you can specify a start paramater if you want - default is 0:
* ```enumerate(iterable, counter)
```
x = [1,2,3]

for index, item in enumerate(x, 2)
    print(item, "is index", index)
```
***
***
# Iterate over multible item sequences using zip()
* zip is used to iterate over two variables simultaneously - like a zipper
* example WITHOUT zip:
```
a = [1,2,3,4]
b = [1,2,3,5]
are_equal = True

for i in range(len(a)):
    if a[i] != b[i]:
        are_equal = False

print(are_equal)
```
* zip() returns an iterator if tuples (elem-a, elem-b)
* example with zip():
```
a = [1,2,3,4]
b = [1,2,3,5]

zip(a, b)
# returns:  [(1,1),(2,2),(3,3),(4,5)]

for var1, var2 in zip(a, b):
    # Code
```
```
a = [1,2,3,4]
b = [1,2,3,5]

for var1, var2 in zip(a, b):
    if var1 == var2:
        return True
    else:
        return None
```
* the number of loop variables must match the number iterables passed in 
* if the iterables are different lenghts: the iterator stops when the shortes input iterable is exausted
***
***
# The 'else' clause
* you can add else clauses to your loops
```
while <condition>:
    # Code
    if <condition>:
        break
else:
    # Code
```
* the else caluse runs when no break statement occurs in the body of the loop
    * for loops - when the iterable is exausted
    * while loops - when the condition becomes false
* these are commonly uses in searches - used when you search and nothing is found
* the advantage is that you dont have to use a flag variable to check if the element was found or not
* here is an example of what the code would look like if you didnt use the else clause:
```
numbers = [1,2,3,4]
even_found = False

for number in numbers:
    if number % 2 == 0:
        print("Even")
        even_found = True
        break

if not even_found:
    print("all numbers were odd")

```
* the better solution:
```
numbers = [1,2,3,4]

for number in numbers:
    if number % 2 == 0:
        print("Even")
        break
else: 
    print("All numbers were odd")
```