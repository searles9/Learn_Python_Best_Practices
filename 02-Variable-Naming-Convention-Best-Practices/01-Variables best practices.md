***
# Variable Naming Conventions and Best Practices
***
***
# Naming styles
* naming styles for identifiers like - variables, constants, functions, classes
* naming doesnt affect the functionality - it just improoves the readability 
## Commonly used naming conventions
* single lowercase letter
    * loop variables - ```i``` and ```j```
* single uppercase letter
* full lowercase name
* lowercase with underscore ```name_var_three``` (snake case)
* full uppercase
    * typically used with constants 
* full uppercase with underscores
* capitalized words ```VarThree``` (camel case - pascal case)
    * typically used with classes
    * upper camel case ```VarThree```
    * lower camel case ```camelCase```

# Bad naming styles
* capitalized words with underscores ```Var_Three_Four```
***
***
# Variable naming rules and conventions
## Rules
* a variable name must start with a letter or underscore
* a variable name cannot start with a number
* variable names can only contain alphanumeric characters and underscores
* variable names are case sensitive 
* variables cannot contain spaces
## Styles
* variables should be written in lowercase with words seperated by underscores ```variable_one``` ... ```snake_case``` (same with function names)
***
***
# Variable naming best practices
* choose meaningful names
* dont use variable names that dont represent thier actual value
    * a variable named ```clients_list``` should not be a tuple
* variables should be meaningful and distinct
* variable named should be pronounceable .... ```player_score``` is better than ```plr_score```
***
***
# Variable names to avoid
* dont use lowercase ```l``` as a single character variable (larry)
* dont use uppercase ```O``` as a single character variable (oliver)
***
***
# How to solve naming conflicts with Python keywords
* keywords are reserved words that cannot be used as variable names, function names or any other identifier 
* to see the python keywords in the interactive shell.... ```help()``` then ```keywords```
* if you need to use one of the keywords you can add a single trailing underscore... ```list_```.... ```class_```
***
***
# Constants in Python
* a constant is a value that cannot change during the execution of the program
* constants are usually written on a module level and are written in all capital letters with underscores seperating words.... ```MAX_OVERFLOW``` or ```TOTAL```
* ```CONSTANT_NAME```
* In Python you cant actually create constants that cant change, but you can recognize the naming convention and not change thier values 
***
*** 
# Boolean variables
* boolean variables should typically start with ```is``` or ```has```
* EX: ```is_valid``` or ```has_pets``` or ```has_children``` or ```is_logged_in```