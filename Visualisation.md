


# Table of Contents
**[MATPLOTLIB](#MATPLOTLIB)**
- [ABOUT](#ABOUT)
    - [Import](#Import)
    - [Show](#Show)
    - [Close](#Close)
- [FORMATTING](#FORMATTING)
    - [Labels](#Labels)
    - [Legend](#Legend)
    - [Set Axis](#Set-axis)
    - [Modify Ticks](#Modify-Ticks)
    - [Subplot](#Subplot)
    - [Figure](#Figure)
- [LINE GRAPHS](#LINE-GRAPHS)
    - [Multiple](#Multiple) 
    - [Line Format](#Line-format)
    - [Shade Error](#Shade-eror)
- [BAR GRAPHS](#BAR-GRAPHS)
    - [Multiple](#Multiple)
    - [Stacked](#Stacked)
    - [Error Bars](#Error-bars)
- [PIE CHART](#PIE-CHART)
- [HISTOGRAM](#HISTOGRAM)
    - [Multiple](#Multiple)
- [SCATTER](#SCATTER)
    - [3D](#3D)


# MATPLOTLIB

## ABOUT
- used to create graphs and charts
- if x_values are strings then x_values = range(len(string_list))

### Import
```
from matplotlib import pyplot as plt
```

### Show
- `plt.show()`

### Close
- `plt.close('all')`: closes all plots including those that may not have been displayed
- `plt.clf` : closes current figure


## FORMATTING

### Labels
- `plt.xlabel('title_string')`
- `plt.ylabel('x_name_string')`
- `plt.title('y_name_string')`

### Legend
- `plt.legend(['label1', 'label2'], loc=#)` : loc positions the legend (defult is best), if specify in .plot() dont need to include list of labels
    - 0 : best
    - 1 : upper right
    - 2 : upper left
    - 3 : lower left
    - 4 :lower right
    - 5 : right
    - 6 : center left
    - 7 : center right
    - 8 : lower center
    - 9 : upper center
    - 10 : center

### Set axis
```
plt.axis(arg)
```
- `plt.axis([min_x, max_x, min_y, max_y])` : zoom in on graph with specs
- `plt.axis('equal')` : shape a circle properly i.e. pie chart

### Modify ticks
```
ax = plt.subplot(args)
plt.plot(args)
ax.set_xticks([values_for_ticks])
ax.set_yticks([values_for_ticks], rotation=#)
```
- `ax` : an axes object, allows to modify axes in subplot
- `ax.set_xticklabels([label_names_for_ticks])`
- `ax.set_yticklabels([label_names_for_ticks])`

### Subplot
```
plt.subplot(#rows, #cols. index_plot_creating)
plt.plot()
```
- display two lines side-by-side in different axis, same figure
- any `plt.plot()` called after subplot will create line in that subplot
- `plt.subplots_adjust(op_args=value)` customise spacing between subplots
    - `left` : left-side margin (default of 0.125)
    - `right` : right-side margin (default of 0.9) 
    - `bottom` : bottom margin, with a default of 0.1
    - `top` : top margin, with a default of 0.9
    - `wspace` : the horizontal space between adjacent subplots, with a default of 0.2
    - `hspace` : the vertical space between adjacent subplots, with a default of 0.2

### Figure
- is the picture/object that contails all of the subplots
`plt.figure(figsize=(width, height))` : creates a new figure
`plt.savefig('name_of_graph.png')` : save as png, cbg, pdf


### Figures and Subplots
```
fig = plt.figure()
fig.add_subplot()
```
- add subplot to a figure

## LINE GRAPH
```
plt.plot(x_values, y_values, color='color_name', linestyle='style', marker='marker', label='for_legend', linewidth=#width)
```
- visualise how a variable changes over time
- `plt.plot(x_values, y_values)` : values1 vs. values2 = y_values vs. x_values

### Multiple
```
plt.plot(x1, y1)
plt.plot(x2, y2)
```
- call plot twice to have multiple line graphs on same axis

### Line Format
- color can be HTML color name or HEX name
- linestyle changes the line
    - `--` : dashed
    - `:` : dotted
    - ` ` : no line
- marker sets style for data points
    - `o` : circle
    - `s` : square
    - `*` : star

### Shade Error
```
y_lower = [i - error_value for i in y_values]
y_upper = [i + error_value for i in y_values]
plt.fill_between(x_values, y_lower, y_upper, aplha=transp_amount)
```
- create shaded error region, then plot line over it
- alpha transparency amount between 0 and 1


## BAR CHART
```
plt.bar(x_values, y_values)
```
- compare multiple categories of data
- the x-values — a list of x-positions for each bar
- the y-values — a list of heights for each bar

### Multiple
```
x_values1 = [t*element + w*n for element
             in range(d)]
```
- do this for both datasets (changing n for each)
    - n = # This is our first dataset (out of 2)
    - t = # Number of datasets
    - d = # Number of sets of bars
    - w = # Width of each bar (default is 0.8)

### Stacked
```
plt.bar(x1, y1)
plt.bar(x2, y2, bottom=y1)
```
- first set normal (will be bottom), second set with `bottom` set to first y (will be top)

### Error Bars
```
plt.bar(x_values, y_values, yerr=error_value, capsize=cap_width)
```
- caps: horizontal lines at top and bottom
- set error_value to be a list to have a different amount of error for each bar 

## PIE CHART
```
plt.pit(data_list, 
        labels=category_list, 
        autopct='format', 
        colors=list_colors
        shadow=True
        startangle=#
        pctdistance=#
        explode=explode)
```
- display elements as a proportions of a whole
- `plt.axis('equal')` : almost always need to use to reshape properly
- autopct : shows percentage on each slice with set format
    - '%0.2f' — 2 decimal places
    - '%0.2f%%' — 2 decimal places, but with a percent sign at the end
    - '%d%%' — rounded to the nearest int and with a percent sign at the end
- `explode = (0.1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0)` : the offeset for each slice i.e. apply 0.1 offset to slice one so it is seperated from the rest of the chart

## HISTOGRAM
```
plt.hist(dataset, range=(min, max), bins=#bins)
```
- shows how many values in a dataset fall bbetween sets of numbers
- width of each bin is distance been min and max (same)
- height is the number of elements that fall in that bin
- default #bins = 10

### Multiple
```
plt.hist(a, range=(min, max), bins=#bins, alpha=#transp, normed=true)
plt.hist(b, range=(min, max), bins=#bins, alpha=#transp, normed=true)
```
- call plt.hist() twice before plt.show()
- `alpha=#transp` : 0 is entirely transparent, 1 is opaque
- `histtype='step` : just show outline instead of alpha
- `normed=True` : normalise histograms (good when different sample sizes)
- `linewidth=#width`

## SCATTER
```
plt.scatter(x_values, y_values)
```

### 3D
```
fig_3d = plt.figure()
fig_3d.add_subplot(1,1,1,projection='3d')
plt.scatter(x,y,z)
```

# SEABORN

## ABOUT
- based on Matplotlib, but improves
- provides a more visually appealing plotting style and concise syntax.
- natively understands Pandas DataFrames, making it easier to plot data directly from CSVs.
- easily summarize Pandas DataFrames with many rows of data into aggregated charts.

### Import
```
import seaborn as sns
```

### Show
```
plt.show()
```

### Setup
```
f, ax = plt.subplots(figsize=(width,height))
```

## FORMATTING


### Labels
`ax.set_title()` : same as `plt.title()`

### Modify Ticks
```
import matplotlib.ticker as mtick
fmt = '${x:,.0f}'
tick = mtick.StrMethodFormatter(fmt)
ax.yaxis.set_major_formatter(tick)
```
- add $ to tick names on y-axis

### Style
```
sns.set_style('style')` 
```
- default is 'darkgrid'
- built in themes : darkgrid, whitegrid, dark, white, ticks
- background colours : dark, white, tick
- grids: whitegrid, white(no grid)

### Despine
```
sns.despine()
```
- change usage of spines i,e, the borders of the figure
- removes top and right spines
- `(left=True)` : pass in to also remove other spinrs
- normal default without this call is four spines
- must call have sns.plot_func()

### Scale
```
sns.set_context('scale_type', font_scale=text_size, rc={"grid.linewidth": 5})
```
- scale_type : presets = paper, notebook(default), talk, poster
- rc: run command, override one of the commands called with scale_type
    - poster = 
```
{'axes.labelsize': 17.6,
 'axes.titlesize': 19.200000000000003,
 'font.size': 19.200000000000003,
 'grid.linewidth': 1.6,
 'legend.fontsize': 16.0,
 'lines.linewidth': 2.8000000000000003,
 'lines.markeredgewidth': 0.0,
 'lines.markersize': 11.200000000000001,
 'patch.linewidth': 0.48,
 'xtick.labelsize': 16.0,
 'xtick.major.pad': 11.200000000000001,
 'xtick.major.width': 1.6,
 'xtick.minor.width': 0.8,
 'ytick.labelsize': 16.0,
 'ytick.major.pad': 11.200000000000001,
 'ytick.major.width': 1.6,
 'ytick.minor.width': 0.8}
```

### Palettes
```
sns.set_palette('palette_name')
```
- if not called will use default colours
- defaults: depp, muted, pastel, bright, dark, colorblind
- `sns.color_palettte(list_of_colours)`: create own pallette and then call set, or pass in name of a [**color brewer**](https://colorbrewer2.org/#type=sequential&scheme=YlGn&n=9) palette and # of variables 
- `sns.palplot(palette_var_name)` : visualise colours of palette


| Palette       | When to use          | About          |
| --------------|:---------------------:| ------------------            |
| qualitative   | distinct but non-ordered categories | set of distinct olours, easy to distinguish categories, no particular ordering/meaning           |
| sequential  | a variable exists as ordered categories , or as continuous values that can be put into groups | move sequentially from a lighter to a darker color, only when high values need to be emphasised           |
| diverging  | both the low and high values might be of equal interest | dark to light to dark, dark more important as attract attention           |


### Seaborn color to matplotlib plot
```
sns.set()
for col in 'xy':
  plt.hist(data[col], normed=True, alpha=0.5)
```

## BARPLOT
```
sns.barplot(data=df, x='x_col_name', y='y_col_name')
```
- by defalt will aggregate `y` and plot mean of each `x`
- sam in matplotlib as subplot() + bar() + xticks() + xticklabels() +xlabel() + ylabel()

### Error Bars
```
sns.barplot(...., ci='error_measure')
```
- adds error bars by default using bootstrapped confidence interval (95%)
- `ci='sd'` : use standard deviation for error bar instead

### Aggregate
```
sns.barplot(...., estimator=aggregate_func)
```
- `np.median` : many outliers
- `len` : categorical and want to count how many times each category appears (eg. survey respones)
- by default calculates mean

### Aggregate by multiple
```
hue='other_x_col_name'
```
- nested categorical value, colour data based on 3rd variable

## DISTRIBUTIIONS

- univariate: only has one variable, one-dimensional
    - KDE plots
    - Box plots 

### KDE PLOTS
```
sns.kdeplot(dataset1, shade=True)
sns.kdeplot(dataset2, shade=True)
```
- Kernel Density Estimator
- sense of a univariate as a curve, shows shape of the data
- preferable to histogra, smooth the datasets, allow to generalise over the shape of our data (not specific data points)
- `shade` : when area under the curve is shaded
- `data` : pandas dataframe, python list, numpy array

### BOX PLOTS
```
sns.boxplot(data=df, x='df_x_col', y='df_y_col')
```
- shows range of dataset eg. outliers, where significant portion of data lies
- The box represents the interquartile range
- The line in the middle of the box is the median
- The end lines are the first and third quartiles
- The diamonds show outliers
- x and y are one dimensial set of values

### VIOLIN PLOTS
```
sns.violinplot(data=df, x='df_x_col', y='df_y_col, hue='3rd_variable', split=True)
```
- good for showing multiple distributions at 1 time
- maps each individual data point, get an estimation of the dataset thanks to KDE
- two KDE plots that are symmetrical along the center line
- white dot represent the median
- thick black line in the center of each violin represents the interquartile range
- lines that extend form the center are the confidence intervals  (95%)
- split shows the hue together instead of side by side




### STRIP PLOTS
```
sns.stripplot(x='x', y='y', data=df)
```


# NUMPY
```
import numpy as np
```

- `np.median(df.col_name)` = `df.col_name.median()`