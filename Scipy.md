[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

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

# PROBABILITY PLOT
```
scipy.stats.probplot(measurements, dist="norm", plot=plot_module_name)
```
- probplot generates a probability plot, which should not be confused with a Q-Q or a P-P plot. 
- dist : The default is 'norm' for a normal probability plot.
- fit : Fit a least-squares regression (best-fit) line to the sample data if True (default).
- plot : If given, plots the quantiles and least squares fit. Default is None, which means that no plot is created.
    - plot=matplotlib.pyplot
    - plot=sns.mpl.pyplot