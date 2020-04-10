[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![python_cheat](https://user-images.githubusercontent.com/19520346/78424238-6b504b00-76af-11ea-862a-fb6ee34dd5df.PNG)


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

### About
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

### nested for loops
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




# PANDAS
```
import pandas as pd
```

### Creating CSV
```
column1,column2,column3
value1,value2,value3
```



## Create DataFrame
DataFrame - an object that stores data as rows and columns (like a spreadsheet or SQL table)
- column has a name (string)
- row has an index (integer)
- contains many different data types

### Using dictionary
```
df1 = pd.DataFrame({
'column_name1': ['value1', 'value2'],
'column_name2' : ['value3', 'value4']
})
```
- pass in dictionary, key = column name, value = list of values
- columns must be same length
- columns appear in alphabetical order

### Using lists
```
df2 = pd.DataFrame([
['row1_value1', 'row1_value2', 'row1_value3'],
['row2_value1', 'row2_value2', 'row2_value3'],
],
columns=['column1', 'column2', 'column3'
])
```
- pass in a list of lists, each one represent a row of data
- pass in 'columns' argument for column names

### Using CSV
```
pd.read_csv('file_name.csv')
```

## Exporting Dataframe

### Write to CSV
```
df.to_csv('new_file_name.csv')
```

## Inspect Dataframe
- `df.head(n)` : show first 5 (default) or n rows
- `df.info()` : RangeIndex, datatypes, memory

## Selecting Data

### 1 column (Series)
```
df[key]
or
df.column_name
```

### Multiple columns (Dataframe)
```
new_df = other_df[['col_name1', 'col_name2]]
```

### 1 row (series)
```
df.iloc[index]
```

### Multiple rows (dataframe)
```
df.iloc[start:end]
```
- end not inclusive

### Rows with logic
```
df[(df.col_name1 >= num) & (df.col_name1 <= num2)]
```
- `|` : or
- `&` : and
- `==` : equal
- `!=` : not equal

```
df[df.col_name.isin(['value1', 'value2'])]
```
- selects rows of columns that exist in the given list

### Reset Indices
```
df.reset_index(inplace=True, drop=True)
```
- creates new df with consecutive indices, creates new col 'index' with old indices
- `inplace` : updates original df
- `drop` : removes 'index' column

## Modifying DataFrames

### Add Columns
```
df['col_name'] = ['value`', 'value2']
```
- add different value for each row
- `df['col_name'] = True` : set all row values to the same
- `df['col_name'] = df.col - df.col2` : can do aggregate on each
- `df['new_col'] = ~df.col.isnull()` : Returns True if col is not (~) null

### Rename Columns
```
df.columns = ['new_col1', 'new_col1']
```
- change all the columns

```
df.rename(columns = {
    'old_col': 'new_col1'
},
inplace=True)
```
- update specific columns in original

### Column Operations
```
df['col_name'] = df.col_name.apply(___)
```
- update every value with (___)
- `apply(lower)` : change all values in that column to Lowercase
- `apply(upper)` : uppercase

```
df['new_col'] = df.col_name.apply(lambda)
```
- create new column using lambda
function

### Row operations
```
df['new_col'] = df.apply(lambda, axis=1)
```
- create new column by lambda function on all rows

## Aggregates

### 1 column
```
df.column_name.measurement()
```
- `median()`
- `nunique()`
- `unique()`
- `max()`
- `mean()`
- `count()`

### groupby 1 column
```
df.groupby('column1').column2.measurement()
```
- creates a series 
- `reset_index()` : add at end to convert to dataframe, move indices into own column

### groupby for percentile
```
df.groupby('col1').col2
    .apply(lambda x: np.percentile(x, 75))
    .reset_index()
```
- input to lambda will always be a list
- common use for calculating percentiles

### groupby multiple columns
```
df.groupby(['col1', 'col2']).col3.measurement().reset_index()
```

### Pivot Table
```
df.pivot(columns='ColumnToPivot',
         index='ColumnToBeRows',
         values='ColumnToBeValues')
```
- change rows to column names
- creates a dataframe
- usually include `reset_index()`



