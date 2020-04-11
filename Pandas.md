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



## SELECT DATA

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

## MODIFY   

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


## AGGREGATES

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




