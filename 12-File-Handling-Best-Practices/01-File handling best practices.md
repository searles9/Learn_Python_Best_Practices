***
# File Handling Best Practices
***
***
# Handling files with context managers
* it is reccomended to use with statements
* using with means that the file will be properly closed after its suite finishes - even if an exeption is raises at some point
* using with is shorter than try-finally blocks
* syntax: ```with EXPRESSION as TARGET: # CODE```
* first approach (bad):
```
file = open("path/to/file", <open mode>)

# works with file

file.close()
```
* its better to use the with statement
* the with statement allows the execution of initialization and finalization code around a block of code
* the better approach using with:
```
with open("path/to/file") as file:
    for line in file:
        print(line)
```
***
***
# Open modes
* syntax ```open(filename, mode)```
* modes:
    * ```r``` - read
    * ```r+``` - read and write
    * ```w``` - write to existing file (an existing file with the same name will be erases)
    * ```a``` - opens the file for appending 
* ```r``` is the default if you dont specify a mode
* example:
```
file = open("path/to/file", "w")

# works with file

file.close()
```
***
***
# How to open multible files with context managers 
* multible with statements cannot use implicit continuation so backlashes are acceptable 
* example: 
```
with open("path/to/file") as file_1, \
     open("file") as file_2:
    # Code 
```