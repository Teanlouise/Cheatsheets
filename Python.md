[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![python_cheat](https://user-images.githubusercontent.com/19520346/78424238-6b504b00-76af-11ea-862a-fb6ee34dd5df.PNG)

# Table of Contents
**1. [SYNTAX](#SYNTAX)**
- [Escape Sequences](#Escape-Sequences)
- [Comments](#Comments)
- [Variables](#Variables)
- [Errors](#Errors)
- [Numbers](#Numbers)
- [Calculations](#Calculations)

**2. [STRINGS](#STRINGS)**
- [Concatenate](#Concatenate)
- [Search](#Search)
- [Slicing/Splitting](#Slicing/Splitting)
- [Formatting](#Formatting)
- [Print](#Printing-with-arguments)

**3. [FUNCTIONS](#FUNCTIONS)**
- [Return](#Return)
- [Lambda](#Lambda)
- [Parameters](#Parameters)
- [Arguments](#Arguments)
- [Decorators](#Decorators)

**4. [CONTROL FLOW](#CONTROL-FLOW)**
- [boolean expressions](#boolean-expressions)
- [boolean operators](#boolean-operators)
- [relational operators](#relational-operators)
- [conditional statement](#conditional-statement)
- [try and except](#try-and-except)

**5. [LISTS](#LISTS)**
- [Create](#Create)
- [Combine](#Combine)
- [Sort](#Sort)
- [Index](#Index)
- [Manipulate](#Manipulate)
- [List Comprehension](#List-Comprehension)

**5. [LOOPS](#LOOPS)**
- [for](#for)
- [nested](#nested)
- [while](#while)

**6. [MODULES](#MODULES)**
- [import](#import)
- [datetime](#datetime)
- [random](#random)
- [pylpot](#pylpot)
- [decimal](#decimal)

**7. [DICTIONARIES](#DICTIONARIES)**
- [Add pair](#Add-pair)
- [add multiple pairs](#add-multiple-pairs)
- [update value](#update-value)
- [combine-lists-into-dictionary](#combine-lists-into-dictionary)
- [get value](#get-value)
- [delete pair](#delete-pair)
- [get-all-keys](#get-all-keys)
- [get-all-values](#get-all-values)
- [get both](#get-both)

**8. [FILES](#FILES)**
- [TXT](#TXT) 
  - [read all](#read-all)
  - [read line by line](#read-line-by-line)
  - [read a line](#read-a-line)
  - [write](write#)
  - [append](#append)
  - [old way](#old-way)
- [CSV](#CSV)
  - [import](#import-CSV)
  - [read](#read-CSV)
  - [write](#write-CSV)
- [JSON](#JSON)
  - [import](#import-JSON)
  - [Read](#Read-JSON)
  - [write](#write-JSON)

**9. [CLASSES](#CLASSES)**
- [Define](#Define)
- [Object](#Object)
- [Class Variables](#Class-Variables)
- [Methods](#Methods)
- [Constructors](#Constructors)
- [Instance Variables](#Instance-Variables)
- [Attributes](#Attributes)
- [String representation](#String-representation)
- [Inheritance](#Inheritance)
- [Exceptions](#Exceptions)
- [Interfaces](#Interfaces)
- [Dunder Methods](#Dunder-Methods)

# SYNTAX
- `print(" ")` : result of statement = ouput
- `type(var)` : the data type of var

### Escape Sequences
- `\n` : newline
- `\t`: tabs

### Comments
```
# This is an inline comment

"""
This is a multi-line comment.
So I can write as much as I want.
"""
```

### Variables
```
var_name = var_value
```
- stores a value
- use `=` to assign or update
- names can't have space or symbol, only underscores (`_`), no numbers at start
- Boolean Variables: a variable that is assigned with a bool type
- immutable: can't be changed eg. int, float, strings, tuples
- mutable: can be changed eg. lists

### Errors
- bugs: errors that didn't expect
- debugging: update so there are no bugs 
- **SyntaxError**: something wrong with how written eg. punctuation, mising (), command not where expected
- **NameError**: word that doesn't recognise
- **ZeroDivisionError**: trying to divide by 0
- **KeyError**: trying to get a key that doesnt exist from dictionary
- `IndentError` : dont have the correct indents

### Numbers

- `int` : Integer, whole number
- `float` : Floating-point, decimal number
- **Literal**: actual number, not variable
- `str(num)` : convert num to a string
- `random.randint(a,b)` : returns a random value between a and b (inclusive), need to import random 


### Calculations
- `+`: addition
- `-`: subtraction
- `*`: multiplication
- `/`: division, convert all ints to floats, result is always a float
- standard order of operations
- `**` : exponent
- `%` : modulo, remainder of division (if number is divisible, then % = 0)
- `var += new` : add new to var

### None
- special value, used when cant assign a value yet to a variable
- unique & immutable
- equates to False in `if` statement
- `is None` : check if None = True
- function with no return prints None

# STRINGS
```
"This is a string"
'This is also a string'
```
- list of characters (each with an index)
- immutable (cannot change once been created)
- surrounded by `' '` or `" "`
- be consistent with which is used
- `len(string)` : the number of characters in the string

### Concatenate
- `+` : string concatenation, creates new string
- `'delimiter'.join(string list)` : any delimiter or escape sequence
- `+=` : add to existing string

### Search
- `letter in word` : check if character/s are present in string
- `string1.find(string2)` : return index of first time string2 appears in string1

### Slicing / Splitting
- `string[index1:index2]` : slicing, creates new string
- `string.split('delimeter')` : returns list of substrings, default is spaces, if delimeter is a character in string then taken out and if character at end then get empty string in list, can also use escape sequeances

### Formatting
- `string.lower()`
- `string.upper()`
- `string.title()` : First letter is capitalised
- `string.strip('char')` : removes character(including repeated) from start and end of string, default is whitespace
- `string.replace(char_to_replace, new_char)`
- `"\"string\""` : put `\` in front of special characters so they can still print i.e. string will print with quotation marks

### Printing with arguments
```
'This is {} string'.format(argument1)`

'This is {argument1} string'.format(argument1=argument1)
```
- puts argument 1 in place of {}
- can use keywords when passing in parameters to function as well

# FUNCTIONS

```
def func_name(param1, param2 = default):
    # do something here
    return func_value
```

- **scope**: where variable exists and can be called
- **function definition**: begins with `def` and contains the entire folloing indented block
- **functional calls**: places a function is invoked 
- **function signature**: the name and parameters


### Return
- `return func_value1, func_value2` : return function value: value returned by function, can be multiple
- `var1, var2 = func_name(param1, param2)`: var1 = out1, var2 = out2

### LAMBDA
```
func_name = lambda param: return
```
- shorthand for a function
- param is the input
- return is what is output

```
lambda x: outcome_if_true if conditional else outcome_if_false
```

### Parameters
- parameter: variable passed into function
- formal parameter: placeholder for name of parameter to be passed in 
- default: this value will be used for parameter if none passed in 
- `param=default_value` : those with defaults need to go at end of param list, make sure default is a mutable item (eg. ) or None


## Arguments
- arguments: values passed in function call
- `func_name("hello","name")` :  positional arguments: assignments depend on position in function call

### Positional Argument Unpacking
```
def func_name(*args):
  var_name = args[0]
  for arg in args[1:]:
    #do something
  return var_name
```
- unpacks arguments given by position, args passsed in will be a tuple, can be any number of args (eg. iteate through list of args), put at end of list of params
- `func_name(*arg_names)` : to call

### Keyword Arguments 
- `func_name(param_name=arg_value)`
- pass arguments with names of parameters, explicitly refer to what each argument is assigned
```
def func_name(param_name=None):
  if param_name is None:
    param_name = []
```

### Keyword Argument Unpacking
```
def func_name(**kwargs):
```
- unlimited keyword arguments asa dictionary
- `func_name(**arg_names)`

### Decorators
```
def decorator_name(func_name):
  def wrapper(*args, **kwargs):
    # do stuff
    func_name(*args, **kwargs)
  return wrapper

@decorator_name
def func_name(param):
  # do stuff
```
- add extra to exisitng function
- `@`: func_name called with decorator

# CONTROL FLOW
- program executes from top down, need to include conditions to tell when to execute certain parts of the code

### Boolean Expressions
- expression can only be `True` or `False`
- these are the only `bool` types
- boolean variable: variable assigned with bool type

### Boolean Operators
- logical operators that comine smaller boolean expressions into larger ones
- `and` : both must be True, otherwise False
- `or` : True if either is True
- `not` : reverse boolean value

### Relational Operators
- creates boolean expressions by returning either `True` or `False`
- `==` : Equals
- `!=` : Not Equals
- `>` : Greater than
- `<` : Less than
- `>=` : Greater than or equal to
- `<= :` Less than or equal to

### Conditional statement
```
if (this is True):
    # do something
elif (this is True):
    # and if condition not met
    # do something
else: 
    # none of above conditions have been met
    # do something
```
- once executed one of the lines that is the end of the statement

### Try and Except
```
try:
    # some statement
except ErrorName:
    # this error occured so stop and do this
```

# LISTS
```
list_name = [item1, item2]
```
- Ordered set of objects
- include space after comma
- can have mised data types (including other lists)
- `len(list_name)` : number of elements in list
- `list_name.count(var)` : return the number of times var appears in list

### Create
- `list_name = []` : empty list
- `list(object_name)` : convert object to list
- `range(start, end, step)` : consecutice from start (default is 0) to end (exclusive), increase each value by step

### Combine
- `zip(list1, list2)` : return object that contains list of pairs (each pair has 1 from each)
- `list_name.append(var)` : add var to end of list
- `list_name + [var_name]` : add [var] to list (must be in  a list)

### Sort
- `list_name.sort()` : sort asc, returns None, changes original list
- `sorted(list_name)` : generates new list, doesnt change original list

### Index
`list_name[num]`
- position of element in list
- `list_name[0]` : first element in list
- `list_name[-1]` : last element
- `list_name[-3:]` : last 3 elements
- `list_name[start:end]` : slicing, end is exclusive
- `list_name[:end]` : from start of list to end
- `list_name[start:]` : all in list from start

### Manipulate
- `list_name.pop()` takes the last item off the list


### List Comprehension
- add item to list when if statement true when iterating through list
```
new_list = [item for item in list_name if item if item[0] = '']
```
- true and false response when iterating throug list
```
new_list = [`answer1` if item > 0 else 'answer2' for item in list_name]
```
- manipulate each item in the list
```
new_list = [item + 'something' for item in list_name]
```

# LOOPS

### for
```
for temp_item in list_name:
    # each item in list does this
```
- `break` : stops loop
- `continue` : skips to next i
- `range()` : use to do something # times
```
for i in range(3):
    # do this 3 times
```

### nested
```
for small_list in big_list:
    for item in small_list:
        # do something
```

### while
```
while condition == True:
    # keep going
```

# MODULES

- package code into files or sets of files
- a collection of Python declarations intented to be used as a tool
- also referred to as libraries or packages 
- `package`: directory that holds collection of modules

### Import
```
from module_name import object_name as alias_name
```
- includes all imports at top of file
- `import *` : imports all, but can be risky as overwrites existing


```
from file_name import func_name
```
- use to import files from in same directory
- file_name is without .py

### datetime
```
from datetime import datetime
```
- `datetime.now()` : current time

### random
```
import random
```
- `random.choice(num_list)` : which takes a list as an argument and returns a number from the list
- `random.randint(num1, num2)` : which takes two numbers as arguments and generates a random number between the two numbers you passed in
- `random.sample(range, num)` : that takes a range and a number as its arguments. It will return the specified number of random numbers from that range.

### pyplot
```
from matplotlib import pyplot as plt 
```
- `plt.plot(x, y)` : plots x and y against eachother
- `plt.show()` : prints the plot

### decimal
```
from decimal import Decimal
```
-  `Decimal('#')` - arithmetic acts much more as expected with rounding floating numbers

# DICTIONARIES
```
dict_name = {"key1": value1, "key2": value2}
```
- unordered set of key and value pairs
- add space between pairs as good practice
- keys: numbers or strings, must have a hash value, unchangeable
- values: can be any datatype
- can be mixed
- `empty_dict = {}`
- `len(dict)` : the number of pairs in the dictionary


### Add pair
```
my_dict["new_key"] = "new_value"
```

### Add multiple pairs
```
dict_name.update({pairs})
```

### Update value
```
my_dict["existing_key"] = "new_value_to_replace"

my_dict["existing_key"] += value
```

### Combine lists into dictionary
```
dict_name = {key:value for key, value in zip(list1_name, list2_name)}
```
- list1_name will be key and list2_name will be value

### Get Value
```
dict_name.get(key, value_if_none)
```
- returns the value of the key
- If key doesnt exist returns None or specific value_if_none

OR
```
dict_name['key']
```
- if key doesnt exist will get KeyError  
- can check if exsists first using try and except
``` 
key_to_check = "Landmark 81"
try:
  print(building_heights[key_to_check])
except KeyError:
  print("That key doesn't exist!")
```

### Delete Pair
```
dict_name.pop(key, default_if_none)
```
- need to know key value
- can specify vlaue to return if key doesnt exist
- can be used to add variable and then delete
```
var_name += dict_name.pop(key, default_value)
other_dict_name[other_key] = dict_name.pop(key, default_value)
```

### Get all keys
```
list(dict_name)
```
- returns a list of just the keys

```
dict_name.keys()
```
- returns a dict_keys object, view object, cant modify
- used for list iteration

### Get all values
```
dict_name.values()
```
- returns a value_keys object, view object, cant modify
- used for list iteration

```
list(dict_name.values())
```
- alternative as there is no built in list option for values

### Get both
```
dict_name.items()
```
- returns dict_list object, each element is a tuple
- use to iterate through dictionary
```
for key, value in dict_name.items():
  # do something
```

# FILES
```
with open('file_name.txt', 'r') as file_var:
  # do something
```
- `with` : invokes context manager, which takes care of opening (with open()) then closing after leave indented block
- `r` : read-mode (default)
- `w` : write-mode
- `a` : append-mode

## TXT FILES

### Read all
```
with open('file_name.txt') as file_var:
  file_contents = file_var.read()
```
- get the whole of file_name in 1 string

### Read line by line
```
with open('file_name.txt') as file_var:
  for line in file_var.readlines():
    # do something
```
- read a text file line by line instead of having the whole thing

### Read a line
```
with open('file_name.txt') as file_var:
  first_line = file_var.readline()
  second_line = file_var.readline()
```
- only read a single line at a time
- don't iterate through whole file
- each call of readline() moves to next line

### Write
```
with open('file_name.txt', 'w') as file_var:
  file_var.write("Text to go in file")
```
- `w` paramater indicates to open file in write-mode
- if file_name exists then oit will be completely overwritten

### Append
```
with open('file_name.txt', 'a') as file_var:
    file_var.write("Text to add to file")
```
- `a` paramater indicates to open file in append-mode
- add text on neew line in file_name after exiting text

### Old way
```
file_variable = open('file_name.txt', 'a')
file_variable.write("Text to add")
file_variable.close()
```
- since no `with` must remember to close

## CSV
```
col1, col2, col3
row1_value1, row1_value2, row1_value3
row2_value1, row2_value2, row2_value3
```
- comma seperated values
- first line is the column names

### Import CSV
```
import csv
```

### Read CSV
```
list_to_append = []
with open('file_name.csv', newline='') as file_var:
  file_reader = csv.DictReader(file_var, delimiter=',')
  for row in file_reader:
    list_to_append.append(row['csv_col_name'])
```
- stores as dictionary
- keys of dictionary are col_names (i.e. csv first line) by default
- `newline=''` : so don't accidentally mistake a line break in one of our data field as a new row in CSV
- `delimiter=';'` specifies how seperated, comma is default

### Write CSV
```
data_to_write = [{'col1': row1_value1, 'col2': row1_value2, 'col3': row1_value3},
                {'col1': row2_value1, 'col2': row2_value2, 'col3': row2_value3}]

with open('new_file_name.csv', 'w') as file_var:
  fields = ['col1', 'col2', 'col3']
  output_writer = csv.DictWriter(file_var, fieldnames=fields)

  output_writer.writeheader()
  for item in data_to_write:
    output_writer.writerow(item)
```
- `file_var.writeheader()` : writes all fieldnames as first row in file
- `output_writer,writerow(item)` : writes each value as a line


## JSON
```
{
    'key1': value1,
    'key2': value2,
    'key3': value3,
}
```
- JavaScript Object Notation

### Import
```
import json
```

### Read JSON
```
with open('file_name.json') as file_var:
  data_var = json.load(file_var)
```
- saves as dictionary

### Write JSON
```
data_to_write = {dictionary_values}

with open('new_file_name.json', 'w') as file_var:
  json.dump(data_to_write, file_var)
```

# CLASSES
- defining classes and creating objects is Object Oriented Programming (OOP)
- **Polymorphism**: flexibility in programming, abstract concept, describes the same syntax doing different actions depending on the type of data

### Define
```
class ClassName:
  pass
```
- template for a data type
- describes the kids of information that class will hold and how interact with it
- `pass` : intentially left blank so dont get indentation error

### Object
```
var_name = ClassName(params_for_init)
```
- class must be initiated i.e. create an instance
- class instance = object
- takes a class and turns it into an object
- `type(object)` : returns class it is an instance of
- `__main__.ClassName` : instance of ClassName in current file

 ### Class Variables
```
class ClassName:
  class_var = ""
```
- same data available to every instance of a class
- attribute of an object
- `object_name.class_var` : access the class variable once an instance is created
- `self.class_var` : to access class variable within class methods

### Methods
```
class ClassName:

  def method_name(self, args):
    var_name = self.class_var # do something
```
- functions that are defined as part of a class
- `self`: first argument is always the object that is calling the method
- `object_name.method_name(args)` : call the function, automatically passes object as self
- **override**: replace existing method from base class by adding a different definition for it in the subclass, when call method on subclass it will use this version instead 

### Constructors (`__init__`)
```
class ClassName:
  def __init__(self, param):
    self.param = param
    # do something

```
- initialise a newly created object
- method that is called automatically every time a class is instantiated

### Instance Variables
```
object_name.instance_var = ''
```
- attribute of an object
- data held by an object, not shared by all instances of a class, specific to object
- `object_name.instance_var` : access instance variable of object
- `self.param_var` : best to define instance varibales in constructor

### Attributes
- instance and class variables are both attributes of an object
- `AttributeError` : if try to access attribute that is not instance/class variable
- `hassattr(object_name, attribute_to_check)` : returns True if object has attribute, else False
- `gettattr(object_name, attribute_to_check, default_value)` : return True if has attribute, else default_value
- `dir(object)` : directory, returns list of object attributes
- `__attr_name__` : internal attribute defined automatically by python for all objects


### String Representation (`__repr__`)
```
class ClassName
  def __repr__(self):
    # return a string
```
- default from print() only shows where class defined and memory address
- `__repr__` : overwrite string representation for class, must return a string, only param is self

### Inheritance
```
class BaseClassName:
  def __init__(self, param):
    self.param = param

class SubClassName(BaseClassName)
  def __init__(self, param, param2)
    super().base_class_func_name(param)
    self.param2 = param2
```
- inherit from another class when creating a new class that needs the same code but with distinct usage
- **base class**: also called parent class
- **subclass**: the one inheriting, also called child class
- `issubclass(class_to_check, base_class_name)` : returns true if first arg is a subclass of second arg, else False (TypeError if neither arg is a class)
- `super()` : used to add extra logic to existing method, call the method from the parent class, returns a proxy object 

### Exceptions
```
class NewExceptionName(Exception):
  # do something
  ```
- `Exception` : built in class
- NewException will behave the same as exception with added functionality
- `raise NewException`: call NewException
- `try: ..... except NewException: ...`

### Interfaces
```
class Class1:
  def func1():
    #do stuff
class Class2:
  def func1():
    # do stuff

obj_name.func1()    
```
- two classes have the same method names and attributes i.e. different classes can perform the same operation
- doesn't check which class the object is an instance of 
- useful when it doesnt matter the class of the object only what it can do

### Dunder Methods
```
def __dunder__(self, params):
```
- a way to use polymorphism
- sometimes called 'magic' methods, special behaviour
- `__init__` : called everytime class is instantiated
- `__repr__` : overwrite `print` 
- `__add__`: overwrites `+` functionality
- `__iter__` : overwrites '`iter()`
- `__len__` : overwrites `len()`
- `__contains__` : overwrites `in`




