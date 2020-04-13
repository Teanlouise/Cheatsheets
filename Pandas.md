[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

# Table of Contents
**1. [GETTING STARTED](#GETTING-STARTED)**
- [Import](#Import)
- [View](#View)
- [Creating CSV](#Creating-CSV)

**2. [CREATE](#CREATE)**
- [Using dictionary](#Using-dictionary)
- [Using lists](#Using-lists)
- [Using CSV](#Using-CSV)

**3. [EXPORT](#EXPORT)**
- [Write to CSV](#Write-to-CSV)


**4. [SELECT DATA](#SELECT-DATA)**
- [1 column](#1-column)
- [Multiple Columns](#Multiple-Columns)
- [1 row](#1-row)
- [Multiple Rows](#Multiple-Rows)
- [Rows with logic](#Rows-with-logic)
- [Reset indices](#Reset-indices)

**5. [MODIFY](#MODIFY)**
- [Add columns](#Add-columns)
- [Rename Columns](#Rename-Columns)
- [Column Operations](#Column-Operations)
- [Row Operations](#Row-Operations)

**6. [AGGREGATES](#AGGREGATES)**
- [1 column](#1-column)
- [grouby 1 column](#grouby-1-column)
- [groupby for percentile](#groupby-for-percentile)
- [groupby multiple columns](#groupby-multiple-columns)
- [pivot table](#pivot-table)



# GETTING STARTED

### Import
```
import pandas as pd
```

### View
- `df.head(n)` : show first 5 (default) or n rows
- `df.info()` : RangeIndex, datatypes, memory

### Creating CSV
```
column1,column2,column3
value1,value2,value3
```

# CREATE
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

# EXPORT

### Write to CSV
```
df.to_csv('new_file_name.csv')
```

# SELECT DATA

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

# MODIFY   

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

### Pivot Table
```
df.pivot(columns='ColumnToPivot',
         index='ColumnToBeRows',
         values='ColumnToBeValues')
```
- change rows to column names
- creates a dataframe
- usually include `reset_index()`


# AGGREGATES

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

# DATA CLEANING
- .head() — display the first 5 rows of the table
- .info() — display a summary of the table
- .describe() — display the summary statistics of the table
- .columns — display the column names of the table
- .value_counts() — display the distinct values for a column
- len(df) : return how many rows
- df.concat(other_df)

### Open files
```
import glob

files = glob.glob('file*.csv')
```
- can open multiple files by using regex matching to get the filenames:

### Combile files
```
df_list = []
for filename in files:
  data = pd.read_csv(filename)
  df_list.append(data)

df = pd.concat(df_list)
```
- go through each file, read data into dataframe then combine together

### Reshape table
```
pd.melt(
    frame=df, 
    ids_vars='df_col_keep', 
    value_vars='df_col_to_var', 
    value_name='new_col_values', 
    var_name='new_col_vars')
```
- frame: the DataFrame you want to melt
- id_vars: the column(s) of the old DataFrame to preserve
- value_vars: the column(s) of the old DataFrame that you want to turn into variables
- value_name: what to call the column of the new DataFrame that stores the values
- var_name: what to call the column of the new DataFrame that stores the variables
- variable as  acolumn, row as a seperate observation
- `df.columns([col names])` : after melting to rename columns

### Dealing with duplicates
- .duplicated() : which will return a Series telling us which rows are duplicate rows.
- .drop_duplicates(subset=['col_name']) : remove all rows that are complete duplicates of another row, use subset if only want to check if specific col is duplicated

### Split by Index
`df['new_col'] = df.col.str[indices]`

### Split by character
```
str_split = df.col_name.str.split('_')
df['new_col'] = str_split.str.get(0)
```

### Types
- `df.dtypes` - shows type of each column
- dtypes: gloat int, bool, datetime, timedelta, category, object

### String Parsing (String to Number)
- `df.col_name = pd.to_numeric(df.col_name)`

### Remove regex
- `df.col_name = df.col_name.replace('[\$,]', '', regex=True)`

### Missing Values
- `NaN` : Not a Number - shows when there is missing data
- `df.dropna(subset=['col_name])` : Drop all rows with a missing value (subset means to only drop rows with NaN in set column)
- ` df.col_name = df.col_name.fillna(value)` : replace NaN for all in 1 column wiht value
- `df.fillna(value={'col_name': value, 'col_name2': value2})` : replace Nan for multiple columns with seperate values 

# REGULAR EXPRESSIONS
- special sequences of characters that describe a pattern of text that is to be matched
- operate by moving character by character, from left to right, through a piece of text. When the regular expression finds a character that matches the first piece of the expression, it looks to find a continuous sequence of matching characters.

### Literals
 - Literals: match the exact characters eg. regex a = text a

### Alternation
 - `exp1|exp2`: Alternation - used on regular expression with `|` to match either entire before **or** after

### Character Sets
 - `e[xs]pressions` : character sets - match **one** character from a series of character to allow for matches with incorrect or different spelling those in `[]` are considered possible letter for before and after brackers
 - `e[^s]pressions` : negated character set - negates the set in [] and matches anything that is not there

### WildCards
 - `...` : wildcards - match any characters (letter, number, symbol or whitespace) in length of wild cards (if want an actual period included use `\` in front of `.`)

 ### Ranges
- `[a-c]` : ranges - specify a range of character to match without having to type each character, can also have multiple ranges 
    - `[a-z]` any lowercase 
    - `[A-Z]` any uppercase
    - `[0-9]` any digit
    - `[a-zA-Z]` any alphabetical character

### Shorthand Character classes
- shorthand character classes [negated]: represent character ranges easier
e.g. `\d\s\w\w\w\w\w\w`
    - `\w` the “word character” class represents the regex range [A-Za-z0-9_], and it matches a single uppercase character, lowercase character, digit or underscore [`\W` is negated version] 
    - `\d`: the “digit character” class represents the regex range [0-9], and it matches a single digit character [`\D` is negated version]
    - `\s`: the “whitespace character” class represents the regex range [ \t\r\n\f\v], matching a single space, tab, carriage return, line break, form feed, or vertical tab [`\S` is negated version]

### Groupings
- `I program (python|java)` : grouping - group parts of a regular expression together, limit alternation to part of the regex eg. search for 'I program python or 'I program java'

### Fixed Quantifiers
- `regex{3,7}` : fixed quantifiers - specify exact quantity of a character to match or provide a range to match (will select largest size if found only) eg. `roa{3,4}r match roaaaar if found or roaaar next`

### Optional Quanitifies
- `humou?r`: optional quantifies: can appear 0 or 1 times, ? only aplied to character directly before it (if searching for a ? use \ before it)

### Kleene
- `*`: kleene star - matches character before it 0 or more times
- `+`: kleene plus - matches character before it 1 or more times

### Anchors
- `^start and end$` : anchors - match the text at the start and end of the string respectively