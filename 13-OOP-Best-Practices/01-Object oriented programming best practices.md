***
# Object Oriented Programming Best Practices
***
***
# Class naming conventions 
* class names shoud use upper camel case... 
```
class BankAccount:
```
***
***
# Blank lines in class definitions
* proper spacing:
```
    class SampleClass:
     
        def method_one(self):
            # Code
     
        def method_two(self):
            # Code
     
        def method_three(self):
            # Code
```
***
***
# Public vs Non-Public Attributes
* you should always decide whether a class's methods and instance variables (collectively "attributes") should be public or non-public
* public attributes are those that you expect unrelated clients of your class to use
* non public attributes are not intended to be used by third parties
* if in doubt choose non-public
* public attributes should have no leading underscores
* you should add one leading underscore to non-public methods and instance variables
```
# Non public

class Dog:
    def __init__(self, pet_id):
        self.__pet_id = pet_id     
```
* technically non-public attributes can be accessed but they shoudlnt be 
* if a simple data attribute needs to grow in functional behavior use properties 
***
*** 
# Properties and the @property decorators 
* getter - a method used to get the value of an attribute...
* setter - a method used to set the value of an attribute...
* ex:
```
    class Dog:
     
        def __init__(self, name):
            self._name = name
     
        def get_name(self):
            return self._name
     
        def set_name(self, new_name):
            self._name = new_name 
```
* in python its better to use the @property 
* For simple public data attributes, it is best to expose just the attribute name, without complicated accessor/mutator methods.
* A property is like an attribute with its own getter and setter methods.  
* example:
```
    class BankAccount:
     
        def __init__(self, balance):
            self._balance = balance
     
        @property
        def balance(self):
            return self._balance
     
        @balance.setter
        def balance(self, new_balance):
            if new_balance >= 0:
                self._balance = new_balance
            else:
                print("Please enter a valid balance.")

    my_account = BankAccount(4523)

    # Get the value of balance
    my_account.balance

    # Update the value of balance
    my_account.balance = 7864

    # Check the new value
    my_account.balance
    # output = 7864
```
***
***
# method naming rules
* method names should be lower score seperated by underscores ```my_method```
* use a leading underscore for non public methods ```_display_data```
***
***
# Methods first arguments
* always use self for the first arguments to instance methods
* instance methods need a class instance and they can access the instance through self  (ex: self.radius below)
```
class Circle: 
    pi = 3.14

    def __init__(self, radius):
        self.radius = radius

    def find_area(self):
        return Circle.pi * (self.radius)**2
```
* always use the cls for the first argument to class methods
* class methods dont need a class instance and they cant access the instance but they can access the class using ```cls```
* class method = you dont need to make an instance
* instance method = you need to make an instance of the class
* class method example:
```
class MyClass:
    @classmethod
    def class_method(cls):
        # Code

cls.class_method()
```
***
***
# How to compare object types
* object type comparisons should always use ```isinstance()``` instead of comparing types directly
* dont do this: 
```
if type(<obj> is type(<obj_of_the_class>)):
```
* this is what you should do:
```
if isinstance(<obj>, <class>)
# checks if the object is an instance of the class

isinstance(my_circle, Circle)
```
***
***
# How to import a class
* when importing a class from a class containing module it is usually ok to do this (same folder): ```from myclass import MyClass```
    * myclass is the module
    * MyClass is the class
* if the module is in a different folder do this:```from foo.bar.yourclass import YourClass``` 
    * foo.bar.yourclass is the path to the module
    * YourClass is the class
***
***
# Implement rich comparison methods 
* these are special methods that provide additional functionality to your class when you implement them
    * __eq__ - equal to
    * __le__ - less than or equal to
    * __ne__ - not equal to
    * __gt__ - greater than 
    * __lt__ - less than
    * __ge__ - greater than or equal to 
* define those to customize how the instances in the class are compared
* for example if you have 2 back account instances of a class - you can define a method that can evaluate whether the 2 instances are equal to 
```
class BankAccount:

    def __init__(self, balance):
        self.balance = balance 

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance <= other.balance

nora_acct = BankAccount(4500)
jack_acct = BankAccount(7000)

# is False
nora_acct == jack_acct 
```
* It is best practice to implement all siz operation so that confusion doesnt arise (not just 2 like shown above)
* the functools.total_ordering() decorator provides a tool to generate missing comparison methods
* example use:
```
from functools import total_ordering

@total_ordering
class BankAccount:

def __init__(self, balance):
        self.balance = balance 

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance <= other.balance

    # The decorator will generate the other 4 comparison methods 
```
* the tool may cause slower execution 
***
***
# Inheritance best practices
* If your class is intended to be subclassed, and you have attributes that you do not want subclasses to use, consider naming them with double leading underscores and no trailing underscores. ```__client_id```