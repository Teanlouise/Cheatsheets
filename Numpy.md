[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![numpy](https://user-images.githubusercontent.com/19520346/79702403-02401880-82e8-11ea-81b2-62c1be7ca6b7.png)


# Table of Contents
**1. [GETTING STARTED](#GETTING-STARTED)**
- [Import](#Import)
- [Read CSV](#Read-CSV)

**2. [ARRAYS](#ARRAYS)**
- [Create](#Create)
- [Element-wise operations](#Element-wise-operations)
- [Combine](#Combine)
- [2D](#2D)
- [Select](#Select)
    - [Select from 1D](#Select-from-1D)
    - [Select from 2D](#Select-from-2D)
    - [Logical Operations](#Logical-Operations)

**3.  [STATISTICS](#STATISTICS)**
- [Spread](#Spread)
    - [Variance](#Variance)
    - [Standard Deviation](#Standard-Deviation)
    - [Range](#Range)
    - [Outliers](#Outliers)
- [Quantiles](#Quantiles)
    - [Median](#Median)
    - [Percentiles](#Percentiles)
    - [Quartiles](#Quartiles)
**4. [PLOTS](#PLOTS)**
- [Histogram](#Histogram)
- [Boxplot](#Boxplot)


# GETTING STARTED 

### Import
```
import numpy as np
```

### Read CSV
```
np.genfromtxt('file_name.csv', delimiter=',')
```

# ARRAYS

## Create
```
np.array([#1, #2, #3])
OR 
np.array(list_name)
```
- a special type of list (NumPy arrays are more efficient than lists)
- a data structure that organizes multiple items
- each item can be of any type (strings, numbers, or even other arrays).
- allow you to do element-wise operations

## Element-wise operations
```
np_array_name + #
```
- quickly perform an operation, such as addition, on each element in an array.
- np_array ** 2 : square all
- np.sqrt(np_array) : square root of all

## Combine
```
new_np_array = np_array_1 + np_array_2 + np_array_3
```
- arrays can be added to or subtracted from each other
- all arrays must have the same number of elements.
- each element will be added/subtracted to its matching element.


## 2D
```
np.array([np_array_1, 
         np_array_2,
         np_array_3])
```
- Two-dimensional array =create an array of arrays, a list of lists where each list has the same number of elements
- often use two-dimensional arrays to represent a set of samples


## Select

### Select from 1D
```
np_array_name[index]
```
- zero-indexed numbering, same indexing as regular python

### Select from 2D
```
np_array_name[row,column]
```
- the relationship between the interior arrays is defined in terms of 2 axes. 
- `axis 0` : same column - the values that share the same indexical position
- `axis 1` : same row - the values that share an array
- `:` : selects the entire row/column eg. `a[:,0]` selects all in first column

### Logical Operations
```
array_name[array_name > 5]
array_name[(array_name > 5) | (array_name < 2)]
```
- checks to see whether statement evaluates to True for each item in the array, without having to use a for loop
- combine logical statements to further specify our criteria ()each statement in parentheses and use boolean operators)
- `|` : or
- `&` : and



# STATISTICS

## MEAN

### Average
```
np.mean(survey_array)
OR
np.average(array_nums)
```

### Logical statements
```
np.mean(array_name op #)
```
- eg. `np.mean(survey_array > 8)`
- calculate the percent of array elements that have a certain property (i.e. condition true)
- resulting mean value will be equivalent to the total number of True items divided by the total array length.


### 2D Arrays
```
np.mean(2D_array_name, axis=#)
```
- `axis=1` : Find mean of each interior array (i.e. the rows)
- `axis=0` : Find mean of each index position (i.e. the columns)
- `np.mean(2D_array_name)` : Find mean across all arrays
- calculate the means of the larger array as well as the interior values.

## VARIATION

### Variance
```
np.var(dataset)
```

### Standard Deviation
```
np.std(dataset)
```

### Range
```
np.amin(dataset)
np.amax(dataset)
```
- range = max - min 

### Outliers
```
np.sort(datset)
```
- One way to quickly identify outliers is by sorting our data, Once our data is sorted, we can quickly glance at the beginning or end of an array to see if some values lie far beyond the expected range

## QUANTILES
```
np.quantile(dataset, [list of quantiles])
```
- points that split a dataset into groups of equal size.

| Quantiles           | Split    | Arg                                          |  
| --------------------|:--------:|:--------------------------------------------:|
| 2-quantile (median) | 2 groups | 0.5                                          | 
| quartiles           | 4 groups | [0,25, 0.5, 0.75]                            |
| quintiles           | 5 groups | [0.2, 0.4, 0.6, 0.8]                         | 
| deciles             | 10       | [0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9]| 
| percentiles         | 100      | [0.01, 0.02,....]                            | 

### Median
```
np.median(array_nums)
```

### PERCENTILES
```
np.percentile(patrons, 30)
```

### QUARTILES
```
np.quantile(dataset, Q#)
OR 
np.percentile(dataset, %#)
```
- Q# = number between 0 and 1
- %N = number between 1 and 100
- 0.5 or 50 = the second quartile (Q2), the median, 50th percentile, half below and half data above
- 0.25 or 25 = first quartile (Q1), 25th percentile
- 0.75 or 75= third quartile (Q3), 75th percentile

## HISTOGRAM
```
np.histogram(array_name, range= (min, max), bins = #)
```



# STATISTICAL DISTRIBUTIONS

# Normal Distribution
```
np.random.normal(mean, std, size=#_of_random)

```
 - symmetric, unimodal
 - Normal distributions are defined by their mean and standard deviation. The mean sets the “middle” of the distribution, and the standard deviation sets the “width” of the distribution. A larger standard deviation leads to a wider distribution. A smaller standard deviation leads to a skinnier distribution.
 loc: the mean for the normal distribution
scale: the standard deviation of the distribution
size: the number of random numbers to generate
