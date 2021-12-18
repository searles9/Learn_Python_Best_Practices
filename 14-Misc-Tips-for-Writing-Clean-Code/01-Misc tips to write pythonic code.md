***
# Misc Tips for Writing Pythonic Code
***
***
# Trailing commas best practices
* trailing commas are usually optional except they are mandatory when making a tuple with one element... ``` (5,) ```
* you can add a comma to show that you are going to extend a list:
```
IMAGES = [
    "img1.png",
    "img2.png",
    "img3.png",
]
```
* it does not make sense to have a trailing comma on the same line as the closing delimiter (except in the above case of singleton tuples)
* bad: ```IMAGES = ["img1.png", "img2.png", "img3.png",]```
***
***
# Swap variables with tuple assignments 
```
x = 8
y = 6
```
* sometimes you need to swap the values of variables
* this would work:
```
(x, y) = (y, x)
# variables that you want to assign the values = values
```
***
***
# Reverse a string
* option 1 (better option): ```<str>[::-1]```
* option 2:```".join(reversed("Hello"))```
***
***
# Merged and update dictionaries 
* only works in Python 3.9
```
first_dict = {"a": 1, "b": 2}
second_dict = {"c": 3, "d": 4}
```
* to merge:
```
third_dict = first_dict | second_dict
```
* to merge + update:
```
second_dict |= first_dict
```
***
***
# The map() function
* 