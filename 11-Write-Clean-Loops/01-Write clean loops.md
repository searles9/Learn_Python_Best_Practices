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
* 