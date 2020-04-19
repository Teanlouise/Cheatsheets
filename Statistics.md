[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)


# FIVE-NUMBER SUMMARY
- The minimum, first quartile, median, third quartile, and maximum of a dataset 
- This set of numbers is a great thing to compute when we get a new dataset.

![scipy](https://user-images.githubusercontent.com/19520346/79702400-010eeb80-82e8-11ea-8d3a-3f2759ee6636.png)

# Table of Contents
- [INTERQUARTILE RANGE (IQR)](#INTERQUARTILE-RANGE-(IQR))
- [MODE](#MODE) 

# INTERQUARTILE RANGE (IQR)
```
from scipy.stats import iqr

interquartile_range = iqr(dataset)
```
- IQR = Q3 - Q1
- ignores the tails of the dataset, outliers have little effect
- difference between the first and third quartile
- 50% of the dataset will lie within the interquartile range.
- gives us an idea of how spread out our data is
    - the smaller the IQR = the less variance in our dataset
    - The greater the value = the larger the variance.

# MODE
```
from scipy import stats

stats.mode(array_nums)
```
- most common observation in a dataset.
- returns the mode and its count
- if there are two modes it returns the smallest


![numpy](https://user-images.githubusercontent.com/19520346/79702403-02401880-82e8-11ea-81b2-62c1be7ca6b7.png)


# Table of Contents
- [GETTING STARTED](#GETTING-STARTED)
    - [Import](#Import)
    - [Read CSV](#Read-CSV)
- [ARRAYS](#ARRAYS)
    - [Create](#Create)
    - [Element-wise operations](#Element-wise-operations)
    - [Combine](#Combine)
    - [2D](#2D)
    - [Select](#Select)
        - [Select from 1D](#Select-from-1D)
        - [Select from 2D](#Select-from-2D)
        - [Logical Operations](#Logical-Operations)
- [STATISTICS](#STATISTICS)
    - [Spread](#Spread)
        - [Variance](#Variance)
        - [Standard Deviation](#Standard-Deviation)
        - [Range](#Range)
        - [Outliers](#Outliers)
    - [Quantiles](#Quantiles)
        - [Median](#Median)
        - [Percentiles](#Percentiles)
        - [Quartiles](#Quartiles)
- [PLOTS](#PLOTS)
    - [Histogram](#Histogram)
    - [Boxplot](#Boxplot)


## GETTING STARTED 

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




# Statistics

## Mean

### Average
```
np.mean(survey_array)
OR
np.average(array_nums)
```
- average = total of values / number of values
- useful measurement to get the center of a dataset

### Logical statements
```
np.mean(array_name op #)
```
- calculate the percent of array elements that have a certain property (i.e. condition true)

When np.mean calculates a logical statement, the resulting mean value will be equivalent to the total number of True items divided by the total array length.
np.mean(survey_array > 8)

### 2D Arrays
```
np.mean(2D_array_name, axis=#)
```
- `axis=1` : Find mean of each interior array (i.e. the rows)
- `axis=0` : Find mean of each index position (i.e. the columns)
- `np.mean(2D_array_name)` : Find mean across all arrays
- calculate the means of the larger array as well as the interior values.



## Spread

### Variance
```
np.var(dataset)
```
- numeric representation of the spread of the data 
- the difference between the data and the mean
- difference = X (single data point)− μ (mean)
- measured in units squared
- small number = data is close together, each data point will tend to be close to the mean, and the difference will be small. 
- large number = data spread out, the difference between every data point and the mean will be larger

### Standard Deviation
```
np.std(dataset)
```
- tells us the spread of the data
- better to use than variance 
- computed by taking the square root of the variance
- By finding the number of standard deviations a data point is away from the mean, we can begin to investigate how unusual that datapoint truly is.
- The larger the standard deviation, the more spread out our data is from the center. 
- The smaller the standard deviation, the more the data is clustered around the mean.
- usually expect: 
    - around 68% of your data to fall within one standard deviation of the mean
    - 95% of your data to fall within two standard deviations of the mean
    - 99.7% of your data to fall within three standard deviations of the mean.
    - over three standard deviations away from the mean = incredibly unusual 

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
- Values that don’t fit within the majority of a dataset
- they can skew our data and lead to error in our analysis
- be useful in pointing out errors in our data collection.
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
- the middle value of a dataset that’s been ordered in terms of magnitude (from lowest to highest).
- the median value can provide an important comparison to the mean. Unlike a mean, the median is not affected by outliers.

### PERCENTILES
```
np.percentile(patrons, 30)
```
- the Nth percentile is defined as the point N% of samples lie below it. 
- useful measurements because they can tell us where a particular value is situated within the greater dataset.

### QUARTILES
```
np.quantile(dataset, Q#)
OR 
np.percentile(dataset, %#)
```
- Q# = number between 0 and 1
- %N = number between 1 and 100
- split the data into fourths
- 0.5 or 50 = the second quartile (Q2), the median, 50th percentile, half below and half data above
- 0.25 or 25 = first quartile (Q1), 25th percentile
- 0.75 or 75= third quartile (Q3), 75th percentile
- there is no universally agreed upon method of calculating quartiles
    1. Q1 and Q3 don't include Q2 
    - Q1 = take all of the data points smaller than Q2 and find the median
    - Q3 =  do the same process using the points that are larger than Q2.
    2. Q1 and Q3 include Q2 
    - include Q2 when calculating median from data points above and below for Q1 and Q3
- Even: One of the more common ways is to take the average of those two numbers.




















# PLOTS

### Histogram
```
np.histogram(array_name, range= (min, max), bins = #)
OR 
plt.hist(array_name, range= (min, max), bins = #, edgecolor = 'black')
```
- reveal, through numbers, interpretable trends in your data
- summarize data that you can use to inform a decision or explain a distribution.
- The two key features of a histogram are bins and counts.
    - A bin is a sub-range of values that falls within the range of a dataset,  width of each bin is the distance between the minimum and maximum values of each bin, All bins in a histogram are always the same size
    - A count is the number of values that fall within a bin’s range.


1. Find the center
```
.mean()
.median()
```

2. Find the range
```
.min()
.max()
Range = max - min
```

3. Find the shape
- Skew = description of the data’s symmetry.

| Skew         | Peak    | Tails   | Median/Mode   | 
| -------------|:--------| --------|:--------------| 
| Symmetric    | one     | similar | similar       |
| Skew-right | left    | right   | median < mean |
| Skew-left  | right   | left    | median > mean |


4. Modality
- describes the number of peaks in a dataset. 
    - Unimodal:  one distinct peak, most common.
    - Bimodal: has two distinct peaks.
    - multimodal: more than two peaks
    - uniform distributions: no obvious clustering.

5. Outliers
- a data point that is far away from the rest of the dataset.
- do not have a formal definition
- easy to determine by looking at histogram
- often indicate an error in your data or an interesting insight.







### BOXPLOTS
```
plt.boxplot(dataset)
or
plt.boxplot([dataset1, dataset2])
```
- one of the most common ways to visualize a dataset
- give you a sense of the central tendency and spread of the data.

- line in the center of the box = median (may not be exactly in middle of box)
- edges of the box = first and third quartiles. 
- box length = interquartile range (the middle 50% of data)
- whiskers = spread of dataset. There are many different ways to calculate the length of the whiskers.
    - closest point that is 1.5 * IQR from Q1 and Q3 (eg. Q1 - (1.5*IQR))
    - min and max
    - one standard deviation from mean
- dots beyond whiskers = outliers 



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
