[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)


# FIVE-NUMBER SUMMARY
- The minimum, first quartile, median, third quartile, and maximum of a dataset 
- This set of numbers is a great thing to compute when we get a new dataset.





# CENTRAL TENDENCY
- most common

### Mean
```
df.column_name.mean()

np.mean(dataset)

np.average(dataset)
```
- average
- interested in outliers
- average = total of values / number of values
- useful measurement to get the center of a dataset

### Median
```
df.column_name.median()

np.median(dataset)
```
- midpoint when ordered
- not interested in outliers

- the middle value of a dataset that’s been ordered in terms of magnitude (from lowest to highest).
- the median value can provide an important comparison to the mean. Unlike a mean, the median is not affected by outliers.

### Mode
```
stats.mode(array_nums)
```
- most frequent occurring


# VARIATION
- spread of data

## Variance 
```
np.var(dataset)
```
- standard deviation **2
- numeric representation of the spread of the data 
- the difference between the data and the mean
- difference = X (single data point)− μ (mean)
- measured in units squared
- small number = data is close together, each data point will tend to be close to the mean, and the difference will be small. 
- large number = data spread out, the difference between every data point and the mean will be larger


## Standard Deviation
```
np.std(dataset)
```
- good when using mean
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

## Ranges

### Max, Min
```
df.column_name.min()
df.column_name.max()

np.amin(dataset)
np.amax(dataset)
```

### Interquartile Range
```
stats.iqr(dataset)
```
- inter-quartile (25-75%)
- good if using median
- q(0.75) - q(0.25) = spread in centre
- standard measure for comparing univariate 

### Boxplots


## Skewness
- (mean-mode) / s
- left skew = -ve
- right skew = +ve
- symmetric = 0

- Skew = description of the data’s symmetry.

| Skew         | Peak    | Tails   | Median/Mode   | 
| -------------|:--------| --------|:--------------| 
| Symmetric    | one     | similar | similar       |
| Skew-right | left    | right   | median < mean |
| Skew-left  | right   | left    | median > mean |

## Kurtosis
- flat/sharp
- not used often

## Modality
- describes the number of peaks in a dataset. 
    - Unimodal:  one distinct peak, most common.
    - Bimodal: has two distinct peaks.
    - multimodal: more than two peaks
    - uniform distributions: no obvious clustering.

## Outliers
- Values that don’t fit within the majority of a dataset
- they can skew our data and lead to error in our analysis
- be useful in pointing out errors in our data collection.

- a data point that is far away from the rest of the dataset.
- do not have a formal definition
- easy to determine by looking at histogram
- often indicate an error in your data or an interesting insight.


# QUANTILES
```
np.quantile(dataset, [list of quantiles])
```
- some number where approximate fraction of data
    - f= 0.50   ~ 1/2 data <= q(0.50)     median
    - f = 0.25  ~ 1/4 data <- q(0.25)     lower quartile (25%)
    - f = 0.75  ~ 3/4 data <- q(0.75)     upper quartile (75%)
- falls on datapoint then no problem, but no set method to calculate them
- interpolation is most common
sort -> location fNth -> VfN+1 - VfN -> q(f)
f=0.5 -> fN=10 -> V11-V10 -> 69-68 -> q(0.5) = 68.5

| Quantiles           | Split    | Arg                                          |  
| --------------------|:--------:|:--------------------------------------------:|
| 2-quantile (median) | 2 groups | 0.5                                          | 
| quartiles           | 4 groups | [0,25, 0.5, 0.75]                            |
| quintiles           | 5 groups | [0.2, 0.4, 0.6, 0.8]                         | 
| deciles             | 10       | [0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9]| 
| percentiles         | 100      | [0.01, 0.02,....]                            | 

### Percentiles
```
np.percentile(patrons, 30)
```
- the Nth percentile is defined as the point N% of samples lie below it. 
- useful measurements because they can tell us where a particular value is situated within the greater dataset.

### Quartiles
```
np.quantile(dataset, Q#)
OR 
np.percentile(dataset, %#)
```
- split the data into fourths
- 0.5 = the second quartile (Q2), the median, 50th percentile, half below and half data above
- 0.25 = first quartile (Q1), 25th percentile
- 0.75 = third quartile (Q3), 75th percentile
- there is no universally agreed upon method of calculating quartiles
    1. Q1 and Q3 don't include Q2 
    - Q1 = take all of the data points smaller than Q2 and find the median
    - Q3 =  do the same process using the points that are larger than Q2.
    2. Q1 and Q3 include Q2 
    - include Q2 when calculating median from data points above and below for Q1 and Q3
- Even: One of the more common ways is to take the average of those two numbers.









