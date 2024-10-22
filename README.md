in order to do data analysis in Python, we should first tell you a little bit about the main packages relevant to analysis in Python. A Python library is a collection of functions and methods that allow you to perform lots of actions without writing any code. The libraries usually contain built-in modules providing different functionalities which you can use directly.
There are extensive libraries offering a broad range of facilities. We have divided the Python data analysis libraries into three groups. The first group is called Scientific Computing Libraries. Pandas offers data structure and tools for effective data manipulation and analysis. It provides fast access to structured data. The primary instrument of Pandas is a two dimensional table consisting of column and row labels, which are called a data frame. It is designed to provide easy indexing functionality. The NumPy library uses arrays for its inputs and outputs.
It can be extended to objects for matrices,
and with minor coding changes,
developers can perform fast array processing.
SciPy includes functions for
some advanced math problems as listed on this slide,
as well as data visualization.
Using data visualization methods is the best way to
communicate with others, showing
the meaningful results of analysis.
These libraries enable you to create
graphs, charts, and maps.
The Matplotlib lib package is
the most well-known library for data visualization.
It is great for making graphs and plots.
The graphs are also highly customizable.
Another high-level visualization library is Seaborn.
It is based on Matplotlib.
It's very easy to generate various plots,
such as heat maps, time series, and violin plots.
With machine learning algorithms,
we're able to develop a model using
our data set and obtain predictions.
The algorithmic libraries tackle
some machine learning tasks from basic too complex.
Here we introduce two packages.
The Scikit-learn library contains tools,
for statistical modeling, including regression,
classification, clustering, and so on.
This library is built on NumPy,
SciPy, and Matplotlib.
Statsmodels is also
a Python module that allows users to explore data,
estimate statistical models,
and perform statistical tests. 
to create a diagram
import matplotlib.pyplot as plt
import numpy as np
xpts = np.array([1,10])
ypts = np.array([10,33])
plt.plot(xpts, ypts)
plt.show()
to create a list
import numpy
m = numpy.array((1,3,5,8,9,0))
print(m)
to open a csv file
pip install pandas
url= "excel test-csv.csv"
df = pd.read_csv(url)
print(df)
or
url= "excel test-csv.csv"
df = pd.read_csv(url, header=None)
print(df)
to show a n lines
pip install pandas
url= "excel test-csv.csv"
df = pd.read_csv(url)
df.head(n)
to show the last n rows
df.tail(n)
import pandas as pd
info = pd.read_csv('excel test-csv.csv')
print(info)
#to analyse a single colomn
info["name_of_the colomn"].describe()
info.shape
info.info()
#for statistics
info.describe()
#TO SHOW THIS STATISTICS IN A DIAGRAM 
info["number"].plot(kind='box', vert=False, figsize=(1,20))
info["number"].plot(kind='box', vert=False, figsize=(1,20))
#TO SHOW THIS STATISTICS as a curve
pip install spicy
pip install matplotlib 
info["number"].plot(kind='density', figsize=(1,20))
#to show the median and the mean in the curve this is the code for the curve+ median and the mean
ax = df['number'].plot(kind='density', figsize=(14,1))
ax.axvline(df['number'].mean(), color='red')
ax.axvline(df['number'].median(), color='green')
#TO SHOW THIS STATISTICS IN A DIAGRAM 
ax = df['number'].plot(kind='hist', figsize=(14,6))
ax.set_ylabel('age')
ax.set_xlabel('name')
#for example if we want to add 2 years to our age colomn we use the following code
tr["age"] = tr["age"]+2
print(tr)
