[Back to Cheatsheets](https://teanlouise.github.io/cheatsheets/)

![seaborn](./images/title_seaborn.png)

# Table of Contents
**1. [ABOUT](#ABOUT)**
- [Import](#Import)
- [Show](#Show)
- [Setup](#Setup)

**2. [FORMATTING](#FORMATTING)**
- [Labels](#Labels)
- [Modify Ticks](#Modify-Ticks)
- [Style](#Style)
- [Despine](#Despine)
- [Scale](#Scale)
- [Palettes](#Palettes)

**3. [BARPLOT](#BARPLOT)**
- [Error Bars](#Error-bars)
- [Aggregate](#Aggregate)
- [Aggregate by multiple](#Aggregate-by-multiple)

**4. [DISTRIBUTIONS](#DISTRIBUTIONS)**
- [KDE plots](#KDE-plots)
- [Box plots](#Box-plots)
- [Violin plots](#Violin-plots)


# ABOUT
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

# FORMATTING


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

# DISTRIBUTIIONS

- univariate: only has one variable, one-dimensional
    - KDE plots
    - Box plots 

### KDE plots
```
sns.kdeplot(dataset1, shade=True)
sns.kdeplot(dataset2, shade=True)
```
- Kernel Density Estimator
- sense of a univariate as a curve, shows shape of the data
- preferable to histogra, smooth the datasets, allow to generalise over the shape of our data (not specific data points)
- `shade` : when area under the curve is shaded
- `data` : pandas dataframe, python list, numpy array

### Box plots
```
sns.boxplot(data=df, x='df_x_col', y='df_y_col')
```
- shows range of dataset eg. outliers, where significant portion of data lies
- The box represents the interquartile range
- The line in the middle of the box is the median
- The end lines are the first and third quartiles
- The diamonds show outliers
- x and y are one dimensional set of values

### Violin plots
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

