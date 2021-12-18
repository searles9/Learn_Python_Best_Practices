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
* syntax: ```map(<function>, <iterable>)
* it applies the function to all items in the iterable 
* it returns an iterator that applies a function to every item of an iterable yielding the results
```
def convert_to_upper(string):
    return string.upper()

my_list = ["word1", "word2", "word3"]

new_list = map(convert_to_upper, my_list)
```
* you could also do:
```
list(map(str.upper, words_list))
```
***
***
# The walrus operator 
* it assignes values to variables as part of a larger expression ```:=```
* you can use + assign
* syntax: ```<var> := <expression>```
* use case: to avoid repeated function calls if the value returned will be used multible times
* without the operator:
```
if len(a) > 5:
    print(f"List is too long ({len(a)} elements)")

# you are calling len twice
```
* with the operator
```
if (n := len(a)) > 5:
    print(f"List is too long ({n} elements)")
```
* it can be useful with while-loops that compute a value to test loop termination and then need that same var again in the body of the loop
```
message = "Enter a number or 's' to stop: "

while (number := in int(input(message))) ! = 's':
    print(f"You entered {number}")

```
* its helpful in list comprehentions where a value computed in a filtering condition is also needed in the expression body 
```
[clean_name.title() for name in names
 if (clean_name := normalize('NFC', name)) in allowed_name]

 # its assigning the value of clean_name
```
* try to limit the use of the walrus operator to clean cases that reduce complexity and improove readability 
