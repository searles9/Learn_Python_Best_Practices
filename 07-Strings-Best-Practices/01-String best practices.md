***
# String Best Practices
***
***
# Single vs double quotes strings
* both quotes are acceptable:
```
"quote"
'quote'
```
* try to avoid using backlash escape characters...
```
"quote's"

# vs
'quote\'s'
```
***
***
# Whitespaces in String Slicing
* there should be equal amount of whitespace on both sides
```
word[start:stop]
text[1:3]
```
* Bad: ```word[start + offset:end + offset]```
* Better:```word[start+offset : end+offset]```
* Correct: ```word[start:end:step]```
* Bad: ```word[start:end: step]```
* when a slice paramater is immitted the space is ommited.. ```word[:end:step]```
***
***
# String method vs string module
* use the string methods instead of the string module
***
***
# String concatenation
* dont rely on pythons in place string concatenation:
``` a += b``` or ```a = a + b```
* this is something that you would NOT want to do:
```
words = ["Hello", ", ", "World", "!"]

final_string = ""

for elem in words:
    final_string += elem

print(final_String)
```
* The reccomended alternitive is to use the ```"".join()``` form
```
# Iterable = list, tuple, dictionary keys
# "" is the seperator
"".join(<iterable>)

# ex:
words = ["Hello", ", ", "World", "!"]
" ".join(words)
```
***
***
# Checking prefixes and suffixes
* you should use ```.startswith()``` and ```.endswith()``` instead of string slicing
```
"Hello Donovan".startswith("Hello")
```
***
***
# Trailing whitespaces
* ```"text ".rstrip()``` will trip trailing whitespace
* ```" text".lstrip()``` will trim the leading whitespace
* ```"  text  ".strip()``` will trim all leading or trailing whitespace