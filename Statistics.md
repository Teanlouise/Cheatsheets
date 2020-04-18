```
from scipy import stats
import numpy as np
```

# Mean
```
np.average(array_nums)
```
- average = total of values / number of values

# Median
```
np.median(array_nums)
```
- observation in the middle of the dataset

# Mode
```
stats.mode(array_nums)
```
- most common observation in a dataset.
- returns the mode and its count
- if there are two modes it returns the smallest

# Variance
```
np.var(dataset)
```
- numeric representation of the spread of the data 
- the difference between the data and the mean
- difference = X (single data point)− μ (mean)
- measured in units squared
- small number = data is close together, each data point will tend to be close to the mean, and the difference will be small. 
- large number = data spread out, the difference between every data point and the mean will be larger

# Standard Deviation
```
np.std(dataset)
```
- better to use than variance 
- computed by taking the square root of the variance
- By finding the number of standard deviations a data point is away from the mean, we can begin to investigate how unusual that datapoint truly is.
- usually expect: 
    - around 68% of your data to fall within one standard deviation of the mean
    - 95% of your data to fall within two standard deviations of the mean
    - 99.7% of your data to fall within three standard deviations of the mean.
    - over three standard deviations away from the mean = incredibly unusual 

# Range
```
np.amin(dataset)
np.amax(dataset)
```
- range = max - min 

# Histograms
```
np.histogram(array_name, range= (min, max), bins = #)
OR 
plt.hist(array_name, range= (min, max), bins = #, edgecolor = 'black')
```
- reveal, through numbers, interpretable trends in your data
- summarize data that you can use to inform a decision or explain a distribution.
- The two key features of a histogram are bins and counts.
    - A bin is a sub-range of values that falls within the range of a dataset.
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
| Right-skewed | left    | right   | median < mean |
| Left-skewed  | right   | left    | median > mean |


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

# QUANTILES
```
np.quantile(dataset, [list of quantiles])
```
- points that split a dataset into groups of equal size.

| Quantiles           | Split    | Arg   |  
| --------------------|:---------| --------|:--------------| 
| 2-quantile (median)| 2 groups | 0.5                                          | 
| quartiles          | 4 groups | [0,25, 0.5, 0.75]                            |
| quintiles          | 5 groups | [0.2, 0.4, 0.6, 0.8]                         | 
| deciles            | 10       | [0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9]| 
| percentiles        | 100      | [0.01, 0.02,....]                            | 

# QUARTILES
```
np.quantile(dataset, Q#)
```
- Q# = number between 0 and 1
- split the data into fourths
- 0.5 = the second quartile (Q2), the median half below and half data above
- 0.25 = first quartile (Q1)
- 0.75 = third quartile (Q3)
- there is no universally agreed upon method of calculating quartiles
    1. Q1 and Q3 don't include Q2 
    - Q1 = take all of the data points smaller than Q2 and find the median
    - Q3 =  do the same process using the points that are larger than Q2.
    2. Q1 and Q3 include Q2 
    - include Q2 when calculating median from data points above and below for Q1 and Q3
- Even: One of the more common ways is to take the average of those two numbers.

# INTERQUARTILE RANGE (IQR)
```
from scipy.stats import iqr

interquartile_range = iqr(dataset)
```
- IQR = Q3 - Q1
- ignores the tails of the dataset, outliers have little effect


# BOXPLOTS
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


