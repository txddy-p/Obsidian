# Matplotlib

## Scatter plot

When you have a time scale along the horizontal axis, the line plot is your friend. But in many other cases, when you're trying to assess if there's a correlation between two variables, the scatter plot is the better choice. Below is an example of how to use the scatter function

```python
import matplotlib.pyplot as plt
plt.scatter(x,y)
plt.xscale('log') #scales the x-axis to logarithmic
```

## Histogram

plt command for histogram

```python
import matplotlib.pyplot as plt
plt.hist(data) #number of bins is 10 by default
plt.hist(data, numBins) #numBins is now the specified number of bins
```

### Bins

The number of bins is pretty important. Too few bins will oversimplify reality and won't show you the details. Too many bins will overcomplicate reality and won't show the bigger picture. To control the number of bins to divide your data in, you can set the `bins` argument.

`plt.clf()` cleans up the plot so you can restart

## Customisation

### Labels

[xlabel()](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.xlabel.html>), [ylabel()](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.ylabel.html>)  and [title()](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.title.html>)These just add labels as stated.

```python
# Add axis labels
plt.xlabel(xlab)   #xlab, title and ylab are all variables storing strings
plt.ylabel(ylab)

# Add title
plt.title(title)

##Ticks
plt.xticks(tick_val,tick_lab) #replaces on said axis tick_val with tick_lab

##Size
plt.scatter(gdp_cap, life_exp, s = pop) #pop is a list and is used in defining the size parameter in the scatter plot
```

`c = col` can be added to the arguments of the `[plt.scatter()](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.scatter.html>)` function for colours

To change the opacity of the bubbles you set the `alpha` argument to `0.8` inside `[plt.scatter()](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.scatter.html>)`. Alpha can be set from zero to one, where zero is transparent, and one is not transparent.

[plt.text()](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.text.html>) function adds words to the plot.

[plt.grid(True)](<https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.grid.html>) so that gridlines are drawn on the plot

# [[Pandas]]
