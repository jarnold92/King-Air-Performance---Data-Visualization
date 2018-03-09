---
title: Viewing Cruise Data
description: In this exercise, we will view the King Air C90 cruise data

---
## View Cruise data exercise

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 5c3eca1ae9
```
The exercise will show you how to plot three line plots, overlayed on one grid. We
will use the King Air C90GTi cruise data which has been extracted from the POH and 
pre-loaded for you in a DataFrame 'data'.  All libraries (Pandas, Matplotlib, Seaborn)
have also been imported for you.

After plotting the graph, inspect your results!  What does the plot tell you about the 
King Air cruise performance at different altitudes?

`@instructions`

-Filter the data for Weight of 9500lbs, and temperature (TMP) of -20, 0 and 20 degrees.

-Build a line chart, with the cold data drawn with color 'blue', cool data in 'green', and
warm data drawn with 'red'.

-Always label your graphs!  We are plotting 'Pressure Altitude' on the X-Axis and
True Airspeed 'TAS' on the Y-axis.

-Format the margins with 2% edges (0.02) to make the plot more readable

-Don't forget to finish off with a plt.show() command, to actually display the plot.


`@hint`

`@pre_exercise_code`
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

FNAME = 'kingair cruise.csv'

# read datafile
data = pd.read_csv(FNAME)


`@sample_code`
# filter by weight = 9500, and for -20, 0, and 20 degree temperatures
heavy_cold = data.loc[(data["Weight"] == ----) & (data["TMP"] == ---)]
heavy_cool = data.loc[(data["Weight"] == ----) & (data["TMP"] == ---)]
heavy_warm = data.loc[(data["Weight"] == ----) & (data["TMP"] == ---)]

# Create plots by using matplotlib
sns.set()
plt.plot(heavy_cold.PA, heavy_cold.TAS, marker='.', color=------)
plt.plot(heavy_cool.PA, heavy_cool.TAS, marker='.', color=------)
plt.plot(heavy_warm.PA, heavy_warm.TAS, marker='.', color=------)

# Lable the plot axis and plot title
_ = plt.xlabel(-----)
_ = plt.ylabel(-----)
_ = plt.title('Plot of TAS by Altitude')

# Make nice 2% margins, and set legend
plt.margins(----)
plt.legend(('ISA -20', 'ISA', 'ISA +20'))

# draw the plot


`@solution`
# filter by weight = 9500, and for -20, 0, and 20 degree temperatures
heavy_cold = data.loc[(data["Weight"] == 9500) & (data["TMP"] == -20)]
heavy_cool = data.loc[(data["Weight"] == 9500) & (data["TMP"] == 0)]
heavy_warm = data.loc[(data["Weight"] == 9500) & (data["TMP"] == 20)]

# Create plots by using matplotlib
sns.set()
plt.plot(heavy_cold.PA, heavy_cold.TAS, marker='.', color='blue')
plt.plot(heavy_cool.PA, heavy_cool.TAS, marker='.', color='green')
plt.plot(heavy_warm.PA, heavy_warm.TAS, marker='.', color='red')

# Lable the plot axis and plot title
_ = plt.xlabel('Pressure Altitude')
_ = plt.ylabel('TAS')
_ = plt.title('Plot of TAS by Altitude')

# Make nice 2% margins, and set legend
plt.margins(0.02)
plt.legend(('ISA -20', 'ISA', 'ISA +20'))

# draw the plot
plt.show()

`@sct`
```{python}

```


