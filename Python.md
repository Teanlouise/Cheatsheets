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
- [Parameters](#Parameters)
- [Arguments](#Arguments)
- [Return](#Return)
- [Lambda](#Lambda)

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

### Errors
- bugs: errors that didn't expect
- debugging: update so there are no bugs 
- **SyntaxError**: something wrong with how written eg. punctuation, mising (), command not where expected
- **NameError**: word that doesn't recognise
- **ZeroDivisionError**: trying to divide by 0
- **KeyError**: trying to get a key that doesnt exist from dictionary

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


# STRINGS
```
"This is a string"
'This is also a string'
```
- list of characters (each with an index)
- immutable (cannot change once been created)
- surrounded by `' '` or `" "`
- be consistent with which is used
- `len(string)`

### Concatenate
- `+` : string concatenation, creates new string
- `'delimiter'.join(string list)` : any delimiter or escape sequence

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

- scope: where variable exists and can be called

### Parameters
- parameter: variable passed into function
- formal parameter: placeholder for name of parameter to be passed in 
- default: this value will be used for parameter if none passed in 

### Arguments
- arguments: values passed in function call
- `func_name("hello","name")` :  positional arguments: assignments depend on position in function call
- `func_name(param2="name", param1="hello")` : keyword arguments: explicitly refer to what each argument is assigned

### Return
- `return func_value1, func_value2` : return function value: value returned by function, can be multiple
- `var1,var2 = func_name(func_val1, func_val2)`: assign multiple return

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

```
from module_name import object_name as alias_name
```
- includes all imports at top of file
- `import *` : imports all, but can be risky as overwrites existing
- package code into files or sets of files
- a collection of Python declarations intented to be used as a tool
- also referred to as libraries or packages 
- `package`: directory that holds collection of modules

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

### Add pair
```
my_dict["new_key"] = "new_value"
```

### Add multiple pairs
```
dict_name.update({pairs})
```

### Overwrite value
```
my_dict["existing_key"] = "new_value_to_replace"
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
