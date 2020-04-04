[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![python_cheat](https://user-images.githubusercontent.com/19520346/78424238-6b504b00-76af-11ea-862a-fb6ee34dd5df.PNG)

# SYNTAX
- `print(" ")` : result of statement = ouput

### Comments
```
# This is an inline comment

"""
This is a multi-line comment.
So I can write as much as I want.
"""
```

### Strings
```
"This is a string"
'This is also a string'
```
- blocks of text
- surrounded by `' '` or `" "`
- be consistent with which is used
- `+` : string concatenation, creates new string

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


### Numbers

- `int` : Integer, whole number
- `float` : Floating-point, decimal number
- **Literal**: actual number, not variable
- `str(num)` : convert num to a string


### Calculations
- `+`: addition
- `-`: subtraction
- `*`: multiplication
- `/`: division, convert all ints to floats, result is always a float
- standard order of operations
- `**` : exponent
- `%` : modulo, remainder of division (if number is divisible, then % = 0)
- `var += new` : add new to var

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
