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
This exercise will show you how to plot three line plots, overlayed on one grid. We
will use the King Air C90GTi cruise data which has been extracted from the POH and 
pre-loaded for you in a DataFrame _'data'_.  All libraries (Pandas, Matplotlib, Seaborn)
have also been imported for you.

After plotting the graph, inspect your results!  What does the plot tell you about the 
King Air cruise performance at different altitudes?

`@instructions`

* Filter the data for Weight of **9500**lbs, and temperature (TMP) of **-20, 0 and 20** degrees.

* Build a line plot, with the cold data drawn with color _'blue'_, cool data in _'green'_, and
warm data drawn with _'red'_.

* Always label your graphs!  We are plotting _'Pressure Altitude'_ on the X-Axis and
True Airspeed _'TAS'_ on the Y-axis.

* Format the margins with 2% edges (0.02) to make the plot more readable

* Don't forget to finish off with a plt.show() command, to actually display the plot.


`@hint`
-For a weight of 8500 and temperature of -40, this would be coded as 
data["Weight"] == 8500) & (data["TMP"] == -40)

-for a plot color of black, inside the plt.plot command there would be
a parameter of color='black'

-if 5% margins were desired, the plt.margins(0.05) we be correct.

-Dont forget the plt.show() command to display the plot!

`@pre_exercise_code`
import pandas as pd
#import matplotlib.pyplot as plt
#import seaborn as sns

# read datafile
data = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_7459/datasets/kingair_cruise.csv')

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


