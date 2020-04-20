# VISUALISATION

# SOFTWARE
- Matplotlib
- Seaborn


# DATA

### UNIVARIATE DATA
- single variable
- measurement of single quantitative variable
- can be broken into categories
- can look at multivariate separately
- eg. temperature 

### BIVARIATE
- two variables, interested in their relationship
- might expect one to be response to other
- can be looked at individually using univariate scatterplots
- look at data by plotting 2D, starting point
- random scatter means there may not be a pattern
- eg. temperature and windspeed

### MULTIVARIATE
- more than twwo


# CURVE FITTING

## Straight Line
- first bext step
- plot line of best fit, linear regression
- does line represent points? (Qualitative)
- find coeffecient of determination (R**2 - quantitative)
eg. 0.91 so this linear relationship explains 91% of the variation in y
- even if find linear correlation, doesnt tell us if meaningful relationship between data, look for more data to explain relationship
- correlation does not imply causation

### Correlation Coeffecient (R)
- tells relationship
- multiple R's to choose

### Coeffecient of Determination
- R**2 is always 0 or positive

### Pearsons
- standard to use for distributed data and linear relationships (dont do by hand)
- if positive then relationship is positive and positively correlated and both increase together
- negative means as one increases the other decreases
- 1 = largest (100%)
- 0 = no trend, scattered all over
- -1 = negative slope
- undefined = can calculate for perfect horizontal or vertical
- 0 = only means not linear correlation (may still be correlated)

### Spearmans
- not distributed/not linear data


## Least squares
- to fit curve software is looking how far above/below curve the points are, takes those distances and squares them and adds together to find the curve that gives the smallest value to that sum of squares
- reason why people like linear/polynomial fits as there are east/fast algorithms
- non-linear much hard with optimisation problems
- algorithms typically only care about vertical distance
- min sum square never usually write own optimisations
- sum of squares is sensitive to outliers
- ideas works for linear and polynomials

## Residual Inspection
- residuals are vertical distance between data and fitted line
- just plot residuals
- above line (bestfit) = positive
- below line == negative
- not useful for linear fits but non-linear makes easier to judge vertical difference
- subtract curve frim data - is there systematic deviation







