***
# Indentation Best Practices
***
***
# The importance of indentation
* indentation is the placement of a line/block of code further to the right or left
* python uses indentation - other languages like jave use characters like ```{ }``` to seperate code
***
***
# Indentation guidelines (tabs vs spaces)
* Use 4 spaces per indentation level 
```
def foo():
4spaces-#code
```
* spaces are the preferred indentation method 
* only use tabs if the code is already relying on tabs
* spaces - good
* tabs - bad
* python 3 disallows the mixing of tabs and spaces for indentation 
## Hanging indentation
* A type-setting style where all the lines in a paragraph are indented except the first line
* In the context of Python, the term is used to describe a style where the opening parenthesis of a parenthesized statement is the last non-whitespace character of the line, with subsequent lines being indented until the closing parenthesis.
* Ex:
```
foo = function_name(
    arg_one, arg_two,
    arg_three, arg_four)
```
* Hanging indents should add a level because we are opening the parentheses and writing the values in the next line. 
***
***
# How to indent/dedent code in idle
* select the code, click ```ctrl``` + ```]```  ...this provides one level of indentation
***
***
# Tabify/untabify code in idle
* tabify means replacing spaces with tabs
* untabify means removing the tabs and replacing them with spaces
* tabify: selct format, tabify region
* untabify: selct format, untabify region
***
***
# Change the number of spaces per level of indentation in idle
* options, configure idle, select the number of spaces
***
***
# Indentation best practices for multi-line conditions
* when a conditional part of an if statement is long enough to require that it be written across multible lines, its worth noting that the combination of a two character keyword (i.e. if) puls a single space, plus an opening parenthesis creates a natural 4 space indent for the subsequent lines of the multi line conditional 
* aka ... ```if + single space + (``` will create a natural indentation for the subsequent lines
* all options below are acceptable
```
if (<condition> and
    <condition2>):
    # code

if (<condition> and
    <condition2>):
    # comment to seperate the code from the conditions visually
    # code

# add extra indentation
if (<condition>
        and <condition2>):
    # code
```
* it is reccomended to write the operator (and or) after the line break like this:
```
if (<condition>
        and <condition2>
        and <condition3>):
    # code
```
***
***