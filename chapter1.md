---
title: Viewing Cruise Data
description: In this exercise, we will view the King Air C90 cruise data

---
## View data exercise

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 5c3eca1ae9
```


`@instructions`

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
_ = plt.xlabel('Pressure Altitude')
_ = plt.ylabel('TAS')
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
