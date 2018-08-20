---
title: "Work on Pandas, Numpy and Matplotlib"
date: 2018-08-20T03:47:50-04:00
draft: false
---

## Work on Numpy, Pandas and Matplotlib

These three libs are really useful in data analysis. I use a piece on dataset in Kaggle to show a little demo of using these libraries.

### Import CVS as data
CVS files cannot be manipulated directly by python, therefore we use Pandas to convert it into what we need.

```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('other-American_B01362.csv')
x = data.values
```
In the code above, data is the DataFrame of Pandas. This is a map structure, we can use 'get(key)' directly get data from DataFrame, or we can cast it into its values -- array of Numpy, which can be easily sliced with Python syntax.

### Try Matplotlib

```
df = pd.DataFrame({"a": np.random.random(100),
                   "b": np.random.random(100),
                   "id": np.arange(100)})

X = df.get("a")
Y = df.get("b")
plt.scatter(X, Y)
plt.show()

```
In this part, we make a Pandas DataFrame by outselves. with Matplotlib library, we draw the scatter plot below.
![sctter plot](https://tuchuang-1256147041.cos.na-toronto.myqcloud.com/Screen%20Shot%202018-08-20%20at%205.46.33%20AM.png)

### After all the preparation above...

We start to put hands on our Kaggle data. I use ''other-American_B01362.csv'' file which we can see in the first code block.

```
a = [0] * 24

for time in data.get("TIME").values:
    judge = time[0:2]
    if(':' in judge):
        hour = int(time[0])
    else:
        hour = int(time[0:2])
    if(hour == 12):
        hour = 0
    if('P' == time[-2]):
        hour += 12
    a[hour] += 1

plt.bar(range(len(a)), a,fc='r')
plt.show

```

In our chart, the X-axis is the time people picked up by uber (1 hour), Y-axis is the number of people picked up in that hour. We can see, in a day, people call uber most at 8:00 A.M. and 11:00 P.M..

![uber chart](https://tuchuang-1256147041.cos.na-toronto.myqcloud.com/Screen%20Shot%202018-08-20%20at%205.27.31%20AM.png)


### Conclusion

After this tiny experienment, we can see:

Pandas got a good DataFrame to deal with raw data, meanwhile Numpy provide very basic functions to manipulate data blocks as arrays with Python syntax.
Matplotlib is a great tool to generate diagrams visualizing what we get from Numpy and Pandas.

##### Reference
[1][https://www.jianshu.com/p/57e3c0a92f3a](https://www.jianshu.com/p/57e3c0a92f3a)

[2][https://matplotlib.org/gallery/statistics/barchart_demo.html](https://matplotlib.org/gallery/statistics/barchart_demo.html)

[3][https://www.kaggle.com/fivethirtyeight/uber-pickups-in-new-york-city](https://www.kaggle.com/fivethirtyeight/uber-pickups-in-new-york-city)













