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
#to analyse a single column
info["name_of_the column"].describe()
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
#for example if we want to add 2 years to our age column we use the following code
tr["age"] = tr["age"]+2
print(tr)
#to drop a ligne or a column with an empty value we use the code
pip install pandas
import pandas as pd
url= 'excel1.csv'
df=pd.read_csv(url)
print (df)
df.dropna(subset=['prefer color'], axis=0, inplace= True) axis =0 drops the entire ligne, axis =1 drops the entire column
print (df)#we only print to see the results
Replace the entries "?" with NaN entry from Numpy library	
df = df.replace("?", np.nan)
Retrieve the data types of the data frame columns	
pf.dtypes
Retrieve the statistical description of the data set. Defaults use is for only numerical data types. Use include="all" to create summary for all variables	
df.describe() #default use df.describe(include="all")
Retrieve the summary of the data set being used, from the data frame	
df.info()
Save the processed data frame to a CSV file with a specified path
df.to_csv(<output CSV path>)
#to access a column
pt= pd{'name of the collumn'}
and now you can amend it as you want
#for dealing with missing values
check with the data collection source
drop the missing values
leave it as missing data
to remove data we use the following code
use dataframes.dropna()
In this video, we'll look at the problem of data with different formats, units, and conventions and the Pandas methods that help us deal with these issues. Data is usually collected from different places, by different people, which may be stored in different formats. Data formatting means bringing data into a common standard of expression that allows users to make meaningful comparisons. As a part of dataset cleaning, data formatting ensures that data is consistent and easily understandable. For example, people may use different expressions to represent New York City, such as N.Y., Ny, NY, and New York. Sometimes this unclean data is a good thing to see. For example, if you're looking at the different ways people tend to write New York, then this is exactly the data that you want. Or if you're looking for ways to spot fraud, perhaps writing N.Y. is more likely to predict an anomaly than if someone wrote out New York in full. But perhaps, more often than not, we just simply want to treat them all as the same entity or format to make statistical analysis easier down the road. Referring to our used car dataset, there's a feature named city-miles per gallon in the dataset, which refers to a car fuel consumption in miles per gallon unit. However, you may be someone who lives in a country that uses metric units, so you would want to convert those values to liters per 100 kilometers, the metric version. To transform miles per gallon to liters per 100 kilometers, we need to divide 235 by each value in the city miles per gallon column. In Python, this can easily be done in one line of code. You take the column and set it to equal to 235 divided by the entire column. In the second line of code, rename column name from city-miles per gallon to city-liters per 100 kilometers using the data frame rename method. For a number of reasons, including when you imported dataset into Python, the data type may be incorrectly established. For example, here we notice that the assigned data type to the price feature is object although the expected data type should really be an integer or float type. It is important for later analysis to explore the feature's data type and convert them to the correct data types. Otherwise, the developed models later on may behave strangely and totally valid data may end up being treated like missing data. There are many data types in Pandas. Objects can be letters or words. Int64 are integers, and floats are real numbers. There are many others that we will not discuss. To identify a feature's data type in Python, we can use the dataframe.dtypes method and check the data type of each variable in a data frame. In the case of wrong data types, the method dataframe.astype can be used to convert a data type from one format to another. For example, using astype("int") for the price column, you can convert the object column into an integer type variable.


In this video we'll be talking about data normalization, an important technique to understand in data preprocessing. When we take a look at the used car data set, we notice in the data that the feature length ranges from 150 to 250, while feature width and height ranges from 50 to 100. We may want to normalize these variables so that the range of the values is consistent. This normalization can make some statistical analyses easier down the road. By making the ranges consistent between variables. Normalization enables a fairer comparison between the different features, making sure they have the same impact. It is also important for computational reasons. Here is another example that will help you understand why normalization is important. Consider a data set containing two features: age and income, where age ranges from 0 to 100, while income ranges from 0 to 20,000 and higher. Income is about 1,000 times larger than age and ranges from 20,000 to 500,000. So these two features are in very different ranges. When we do further analysis, like linear regression, for example, the attribute "income" will intrinsically influence the result more due to its larger value. But this doesn't necessarily mean it is more important as a predictor. So the nature of the data biases the linear regression model to weigh income more heavily than age. To avoid this, we can normalize these two variables into values that range from 0 to 1. Compare the two tables at the right. After normalization, both variables now have a similar influence on the models we will build later. There are several ways to normalize data. I will just outline three techniques. The first method, called simple feature scaling, just divides each value by the maximum value for that feature. This makes the new values range between 0 and 1. The second method, called min max, takes each value x underscore old, subtracts it from the minimum value of that feature, then divides by the range of that feature. Again, the resulting new values range between 0 and 1. The third method is called Z-score, or standard score. In this formula, for each value, you subtract the mu, which is the average of the feature and then divide by the standard deviation sigma. The resulting values hover around zero and typically range between negative three and positive three, but can be higher or lower. Following our earlier example, we can apply the normalization method on the length feature. First, we use the simple feature scaling method, where we divide it by the maximum value in the feature. Using the Pandas method max(), This can be done in just one line of code. Here's the min max method on the length feature. We subtract each value by the minimum of that column, then divide it by the range of that column the max minus the min. Finally, we apply the Z-score method on length feature to normalize the values. Here we apply the mean and STD method on the length feature. Mean method will return the average value of the feature in the data set and STD method will return the standard deviation of the features in the data set. [MUSIC]

In this video, we'll be talking about binning as a method of data preprocessing. Binning is when you group values together into bins. For example, you can bin age into 0-5, 6-10, 11-15 and so on. Sometimes binning can improve accuracy of the predictive models. In addition, sometimes we use data binning to group a set of numerical values into a smaller number of bins to have a better understanding of the data distribution. As example, "price" here is an attribute range from 5,000 to 45,500. Using binning, we categorize the price into three bins: low price, medium price and high prices. In the actual car dataset, price is a numerical variable ranging from 5,188 to 45,400. It has 201 unique values. We can categorize them into three bins, low, medium and high price cars. In Python, we can easily implement the binning. We would like three bins of equal bin width, so we need four numbers as dividers that are equal distance apart. First, we use the NumPy function linspace to return the array bins that contains four equally spaced numbers over the specified interval of the price. We create a list group underscore names that contains the different bin names. We use the Pandas function cut to segment and sort the data values into bins. You can then use histograms to visualize the distribution of the data after they've been divided into bins. This is the histogram that we plotted based on the binning that we applied in the price feature. From the plot, it is clear that most cars have a low price and only very few cars have high price. 


Interactive Transcript - Enable basic transcript mode by pressing the escape key
You may navigate through the transcript using tab. To save a note for a section of text press CTRL + S. To expand your selection you may use CTRL + arrow key. You may contract your selection using shift + CTRL + arrow key. For screen readers that are incompatible with using arrow keys for shortcuts, you can replace them with the H J K L keys. Some screen readers may require using CTRL in conjunction with the alt key
Play video starting at ::6 and follow transcript0:06
In this video, we'll discuss how to turn categorical variables into quantitative variables in Python. Most statistical models cannot take in objects or strings as input, and for model training, only take the numbers as inputs. In the car data set, the fuel type feature as a categorical variable has two values; gas or diesel which are in string format. For further analysis, Jerry has to convert these variables into some form of numeric format. We encode the values by adding new features corresponding to each unique element in the original feature we would like to encode. In the case where the feature fuel has two unique values, gas and diesel, we create two new features, gas and diesel. When a value occurs in the original feature, we set the corresponding value to one in the new feature, the rest of the features are set to zero. In the fuel example for car B, the fuel value is diesel. Therefore, we set the feature diesel equal to one and the gas feature to zero. Similarly for car D, the fuel value is gas. Therefore, we set the feature gas equal to one and the feature diesel equal to zero. This technique is often called one hot encoding. In pandas, we can use get_dummies method to convert categorical variables to dummy variables. In Python, transforming categorical variables to dummy variables is simple. Following the example pd.get_dummies method gets the fuel type column and creates the data frame dummy_variable_one. The get_dummies method automatically generates a list of numbers, each one corresponding to a particular category of the variable.

In this video, we'll cover the basics of grouping and how this can help to transform our data set. Assume you want to know, is there any relationship between the different types of drive system, forward, rear, and four-wheel drive, and the price of the vehicles. If so, which type of drive system adds the most value to a vehicle? It would be nice if we could group all the data by the different types of drive wheels and compare the results of these different drive wheels against each other. In Pandas, this can be done using the groupby method. The groupby method is used on categorical variables, groups the data into subsets according to the different categories of that variable, you can group by a single variable, or you can group by multiple variables by passing in multiple variable names. As an example, let's say we are interested in finding the average price of vehicles and observe how they differ between different types of body styles and drive wheels variables. To do this, we first pick out the three data columns we are interested in, which is done in the first line of code. We then group the reduced data according to drive wheels and body style in the second line. Since we are interested in knowing how the average price differs across the board, we can take the mean of each group and append at this bit at the very end of the Line 2. The data is now grouped into subcategories, and only the average price of each subcategory is shown. We can see that according to our data, rear-wheel drive convertibles and rear-wheel drive hardtops have the highest value, while four-wheel drive hatchbacks have the lowest value. A table of this form isn't the easiest to read and also not very easy to visualize. To make it easier to understand, we can transform this table to a pivot table by using the pivot method. In the previous table, both drive wheels and body style were listed in columns. A pivot table has one variable displayed along the columns and the other variable displayed along the rows. Just with one line of code and by using the Pandas pivot method, we can pivot the body style variable so it is displayed along the columns, and the drive wheels will be displayed along the rows. The price data now becomes a rectangular grid, which is easier to visualize. This is similar to what is usually done in Excel spreadsheets. Another way to represent the pivot table is using a heat map plot. Heat map takes a rectangular grid of data and assigns a color intensity based on the data value at the grid points. It is a great way to plot the target variable over multiple variables, and through this, get visual clues of the relationship between these variables and the target. In this example, we use Pyplot's pcolor method to plot heat map and convert the previous pivot table into a graphical form. We specified the red-blue color scheme. In the output plot, each type of body style is numbered along the x-axis, and each type of drive wheels is numbered along the y-axis. The average prices are plotted with varying colors based on their values according to the color bar. We see that the top section of the heat map seems to have higher prices in the bottom section.

from matplotlib import pyplot as plt
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
plt.plot(x,y)
plt.scatter(x,y)
plt.hist(x,bins)
plt.bar(x,height)
sns.regplot(x = 'header_1',y = 'header_2',data= df)


3. Residual Plot

A residual plot is used to display the quality of polynomial regression. This function will regress y on x as a polynomial regression and then draw a scatterplot of the residuals.
Residuals are the differences between the observed values of the dependent variable and the predicted values obtained from the regression model. In other words, a residual is a measure of how much a regression line vertically misses a data point, meaning how far off the predictions are from the actual data points.
sns.residplot(data=df,x='header_1', y='header_2')
sns.residplot(x=df['header_1'], y=df['header_2'])

4. KDE plot

A Kernel Density Estimate (KDE) plot is a graph that creates a probability distribution curve for the data based upon its likelihood of occurrence on a specific value. This is created for a single vector of information. It is used in the course in order to compare the likely curves of the actual data with that of the predicted data.

Syntax:


sns.kdeplot(X)

5. Distribution Plot

This plot has the capacity to combine the histogram and the KDE plots. This plot creates the distribution curve using the bins of the histogram as a reference for estimation. You can optionally keep or discard the histogram from being displayed. In the context of the course, this plot can be used interchangeably with the KDE plot.

Syntax:

1
sns.distplot(X,hist=False)

 



Play


00:00
08:41
Mute

Settings
Chi-Square Test for Categorical Variables
Introduction
The chi-square test is a statistical method used to determine if there is a significant association between two categorical variables. This test is widely used in various fields, including social sciences, marketing, and healthcare, to analyze survey data, experimental results, and observational studies.

Concept
The chi-square test is a non-parametric statistical method used to examine the association between two categorical variables. It evaluates whether the frequencies of observed outcomes significantly deviate from expected frequencies, assuming the variables are independent. The test is grounded in the chi-square distribution, which is applied to count data and helps in determining if any observed deviations could have arisen by random chance.

Null Hypothesis and Alternative Hypothesis
The chi-square test involves formulating two hypotheses:

Null Hypothesis 
(
𝐻
0
)
(H 
0
​
 ) - Assumes that there is no association between the categorical variables, implying that any observed differences are due to random chance.

Alternative Hypothesis 
(
H
1
)
(H 
1
​
 ) - Assumes that there is a significant association between the variables, indicating that the observed differences are not due to chance alone.

Formula
The chi-square statistic is calculated using the formula:

χ
2
=
∑
(
O
i
−
E
i
)
2
E
i
χ 
2
 =∑ 
E 
i
​
 
(O 
i
​
 −E 
i
​
 ) 
2
 
​
 

where
O
i
O 
i
​
  is the observed frequency for category 
i
i.
E
i
E 
i
​
  is the expected frequency for category 
i
i, calculated as:

E
i
=
(
r
o
w
 
t
o
t
a
l
×
c
o
l
u
m
n
 
t
o
t
a
l
)
g
r
a
n
d
 
t
o
t
a
l
E 
i
​
 = 
grand total
(row total×column total)
​
 

The sum is taken over all cells in the contingency table.

The calculated chi-square statistic is then compared to a critical value from the chi-square distribution table. This table provides critical values for different degrees of freedom 
(
d
f
)
(df) and significance levels 
(
α
)
(α).

The degrees of freedom for the test are calculated as:

d
f
=
(
r
−
1
)
×
(
c
−
1
)
df=(r−1)×(c−1)

where 
r
r is the number of rows and 
c
c is the number of columns in the table.

Applications
Market Research: Analyzing the association between customer demographics and product preferences.
Healthcare: Studying the relationship between patient characteristics and disease incidence.
Social Sciences: Investigating the link between social factors (e.g., education level) and behavioral outcomes (e.g., voting patterns).
Education: Examining the connection between teaching methods and student performance.
Quality Control: Assessing the association between manufacturing conditions and product defects.
Practical Example - Weak Correlation
Suppose a researcher wants to determine if there is an association between gender (male, female) and preference for a new product (like, dislike). The researcher surveys 100 people and records the following data:

Category	Like	Dislike	Total
Male	20	30	50
Female	25	25	50
Total	45	55	100
Step 1: Calculate Expected Frequencies

Using the formula for expected frequencies:

E
M
a
l
e
,
L
i
k
e
=
(
50
×
45
)
100
=
22.5
E 
Male,Like
​
 = 
100
(50×45)
​
 =22.5
E
M
a
l
e
,
D
i
s
l
i
k
e
=
(
50
×
55
)
100
=
27.5
E 
Male,Dislike
​
 = 
100
(50×55)
​
 =27.5
E
F
e
m
a
l
e
,
L
i
k
e
=
(
50
×
45
)
100
=
22.5
E 
Female,Like
​
 = 
100
(50×45)
​
 =22.5
E
F
e
m
a
l
e
,
D
i
s
l
i
k
e
=
(
50
×
55
)
100
=
27.5
E 
Female,Dislike
​
 = 
100
(50×55)
​
 =27.5

Step 2: Compute Chi-Square Statistic

χ
2
=
(
20
−
22.5
)
2
22.5
+
(
30
−
27.5
)
2
27.5
+
(
25
−
22.5
)
2
22.5
+
(
25
−
27.5
)
2
27.5
χ 
2
 = 
22.5
(20−22.5) 
2
 
​
 + 
27.5
(30−27.5) 
2
 
​
 + 
22.5
(25−22.5) 
2
 
​
 + 
27.5
(25−27.5) 
2
 
​
 

χ
2
=
(
2.5
)
2
22.5
+
(
2.5
)
2
27.5
+
(
2.5
)
2
22.5
+
(
2.5
)
2
27.5
χ 
2
 = 
22.5
(2.5) 
2
 
​
 + 
27.5
(2.5) 
2
 
​
 + 
22.5
(2.5) 
2
 
​
 + 
27.5
(2.5) 
2
 
​
 

χ
2
=
6.25
22.5
+
6.25
27.5
+
6.25
22.5
+
6.25
27.5
χ 
2
 = 
22.5
6.25
​
 + 
27.5
6.25
​
 + 
22.5
6.25
​
 + 
27.5
6.25
​
 

χ
2
=
0.277
+
0.227
+
0.277
+
0.227
χ 
2
 =0.277+0.227+0.277+0.227

χ
2
=
1.008
χ 
2
 =1.008

Step 3: Determine Degrees of Freedom

d
f
=
(
2
−
1
)
×
(
2
−
1
)
=
1
df=(2−1)×(2−1)=1

Step 4: Interpret the Result

Using a chi-square distribution table, we compare the calculated chi-square value (1.008) with the critical value at one degree of freedom and a significance level (e.g., 0.05). The critical value, as determined from chi-square distribution tables, is approximately 3.841.

Since 1.008 < 3.841, we fail to reject the null hypothesis. Thus, there is no significant association between gender and product preference in this sample.

Practical Example - Strong Association
Consider a study investigating the relationship between smoking status (smoker, non-smoker) and the incidence of lung disease (disease, no disease). The researcher collects data from 200 individuals and records the following information:

Category	Disease	No Disease	Total
Smoker	50	30	80
Non-Smoker	20	100	120
Total	70	130	200
Step 1: Calculate Expected Frequencies

Using the formula for expected frequencies:

E
S
m
o
k
e
r
,
D
i
s
e
a
s
e
=
(
80
×
70
)
200
=
28
E 
Smoker,Disease
​
 = 
200
(80×70)
​
 =28
E
S
m
o
k
e
r
,
N
o
 
D
i
s
e
a
s
e
=
(
80
×
130
)
200
=
52
E 
Smoker,No Disease
​
 = 
200
(80×130)
​
 =52
E
N
o
n
−
S
m
o
k
e
r
,
D
i
s
e
a
s
e
=
(
120
×
70
)
200
=
42
E 
Non−Smoker,Disease
​
 = 
200
(120×70)
​
 =42
E
N
o
n
−
S
m
o
k
e
r
,
N
o
 
D
i
s
e
a
s
e
=
(
120
×
130
)
200
=
78
E 
Non−Smoker,No Disease
​
 = 
200
(120×130)
​
 =78

Step 2: Compute Chi-Square Statistic

χ
2
=
(
50
−
28
)
2
28
+
(
30
−
52
)
2
52
+
(
20
−
42
)
2
42
+
(
100
−
78
)
2
78
χ 
2
 = 
28
(50−28) 
2
 
​
 + 
52
(30−52) 
2
 
​
 + 
42
(20−42) 
2
 
​
 + 
78
(100−78) 
2
 
​
 

χ
2
=
(
22
)
2
28
+
(
22
)
2
52
+
(
22
)
2
42
+
(
22
)
2
78
χ 
2
 = 
28
(22) 
2
 
​
 + 
52
(22) 
2
 
​
 + 
42
(22) 
2
 
​
 + 
78
(22) 
2
 
​
 

χ
2
=
484
28
+
484
52
+
484
42
+
484
78
χ 
2
 = 
28
484
​
 + 
52
484
​
 + 
42
484
​
 + 
78
484
​
 

χ
2
=
17.29
+
9.31
+
11.52
+
6.21
χ 
2
 =17.29+9.31+11.52+6.21

χ
2
=
44.33
χ 
2
 =44.33

Step 3: Determine Degrees of Freedom

d
f
=
(
2
−
1
)
×
(
2
−
1
)
=
1
df=(2−1)×(2−1)=1

Step 4: Interpret the Result

Using a chi-square distribution table, we compare the calculated chi-square value (44.33) with the critical value at one degree of freedom and a significance level (e.g., 0.05), approximately 3.841. Since 44.33 > 3.841, we reject the null hypothesis. This indicates a significant association between smoking status and the incidence of lung disease in this sample.

Conclusion
The chi-square test is a powerful tool for analyzing the relationship between categorical variables. By comparing observed and expected frequencies, researchers can determine if there is a statistically significant association, providing valuable insights in various fields of study.

Congratulations! You have completed this lesson. At this point in the course, you know: 

Tools like the 'describe' function in pandas can quickly calculate key statistical measures like mean, standard deviation, and quartiles for all numerical variables in your data frame. 
Congratulations! You have completed this lesson. At this point in the course, you know: 

Tools like the 'describe' function in pandas can quickly calculate key statistical measures like mean, standard deviation, and quartiles for all numerical variables in your data frame. 

Use the 'value_counts' function to summarize data into different categories for categorical data. 

Box plots offer a more visual representation of the data's distribution for numerical data, indicating features like the median, quartiles, and outliers.

Scatter plots are excellent for exploring relationships between continuous variables, like engine size and price, in a car data set.

Use Pandas' 'groupby' method to explore relationships between categorical variables.

Use pivot tables and heat maps for better data visualizations.

Correlation between variables is a statistical measure that indicates how the changes in one variable might be associated with changes in another variable.

When exploring correlation, use scatter plots combined with a regression line to visualize relationships between variables.

Visualization functions like regplot, from the seaborn library, are especially useful for exploring correlation.

The Pearson correlation, a key method for assessing the correlation between continuous numerical variables, provides two critical values—the coefficient, which indicates the strength and direction of the correlation, and the P-value, which assesses the certainty of the correlation.

A correlation coefficient close to 1 or -1 indicates a strong positive or negative correlation, respectively, while one close to zero suggests no correlation.

For P-values, values less than .001 indicate strong certainty in the correlation, while larger values indicate less certainty. Both the coefficient and P-value are important for confirming a strong correlation.

Heatmaps provide a comprehensive visual summary of the strength and direction of correlations among multiple variables.




Use the 'value_counts' function to summarize data into different categories for categorical data. 

Box plots offer a more visual representation of the data's distribution for numerical data, indicating features like the median, quartiles, and outliers.

Scatter plots are excellent for exploring relationships between continuous variables, like engine size and price, in a car data set.

Use Pandas' 'groupby' method to explore relationships between categorical variables.

Use pivot tables and heat maps for better data visualizations.

Correlation between variables is a statistical measure that indicates how the changes in one variable might be associated with changes in another variable.

When exploring correlation, use scatter plots combined with a regression line to visualize relationships between variables.

Visualization functions like regplot, from the seaborn library, are especially useful for exploring correlation.

The Pearson correlation, a key method for assessing the correlation between continuous numerical variables, provides two critical values—the coefficient, which indicates the strength and direction of the correlation, and the P-value, which assesses the certainty of the correlation.

A correlation coefficient close to 1 or -1 indicates a strong positive or negative correlation, respectively, while one close to zero suggests no correlation.

For P-values, values less than .001 indicate strong certainty in the correlation, while larger values indicate less certainty. Both the coefficient and P-value are important for confirming a strong correlation.

Heatmaps provide a comprehensive visual summary of the strength and direction of correlations among multiple variables.

Correlation matrix created using all the attributes of the dataset.
df.corr()

Correlation matrix created using specific attributes of the dataset.
df[['attribute1','attribute2',...]].corr()

	Create a scatter plot using the data points of the dependent variable along the x-axis and the independent variable along the y-axis.
 from matlplotlib import pyplot as 
plt plt.scatter(df[['attribute_1']],df[['attribute_2']])

Uses the dependent and independent variables in a Pandas data frame to create a scatter plot with a generated linear regression line for the data.
import seaborn as sns 
sns.regplot(x='attribute_1',y='attribute_2', data=df)

Create a box-and-whisker plot that uses the pandas dataframe, the dependent, and the independent variables.
import seaborn as sns 
sns.boxplot(x='attribute_1',y='attribute_2', data=df)

Create a group of different attributes of a dataset to create a subset of the data.
df_group = df[['attribute_1','attribute_2',...]]

a. Group the data by different categories of an attribute, displaying the average value of numerical attributes with the same category.
b. Group the data by different categories of multiple attributes, displaying the average value of numerical attributes with the same category.
a.
df_group = 
df_group.groupby(['attribute_1'],as_index=False).mean() 
b. 
df_group = df_group.groupby(['attribute_1', 
'attribute_2'],as_index=False).mean()

Create Pivot tables for better representation of data based on parameters
grouped_pivot = 
df_group.pivot(index='attribute_1',columns='attribute_2')

Create a heatmap image using a PsuedoColor plot (or pcolor) using the pivot table as data.
from matlplotlib import pyplot as plt 
plt.pcolor(grouped_pivot, cmap='RdBu')

Calculate the Pearson Coefficient and p-value of a pair of attributes
From scipy import stats 
pearson_coef,p_value=stats.pearsonr(df['attribute_1'], 
df['attribute_2'])

Import linear_model from scikit-learn
from sklearn.linear_model import LinearRegression
Create a Linear Regression Object using the constructor:
lm=LinearRegression()

we define the predictor variable and target variable
x = df [ [ 'highway-mpg' ] ]
y = df  [ 'price' ]
then use lm.fit(x, y) to fit the model, i.e find the parameters b0 and b1
we can obtain a prediction
Yhat=lm.predict(x)

Regression plot
import seaborn as sns
sns.regplot(x="highway-mpg", y="price", dta=df)
plt.ylim(0, )

Residual plot
sns.residplot(df['highway-mpg'], df['price'])

Distribution plots
import seaborn as sns
ax1=sns.distplot(df['price'], h

ist=False, color="r", label="Actual Value")
sns.distplot(Yhat, hist=False, color="b", label="Fitted Values", ax=ax1)

calculate polynomial of 3rd order
f=np.polyfit(x,y,3)
p=np.polyld(f)
print(p)

ploynomial regression with more than one dimension
from sklearn.preprocessing import PolynomialFeatures
pr=PolynomialFeatures(degree=2, include_bias=False)
x_polly=pr.fit_transform(x[['horsepower', 'curb-weight']])

Pre-processing
from sklearn.preprocessing import StandardScaler
SCALE=StandardScaler()
SCALE.fit(x_data[['horsepower', 'highway-mpg']])

Pipelines
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import StandardScaler
from sklearn.pipeline import Pipeline
input=[('polynomial', PolynomailFeature(degree=2),('scale', StadardScaler()),...
('Model', LinearRegression())]
pipe=Pipeline(Input)
Pipe.fir(df['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']],y)
yhat=Pipe.predict(X[['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']])

import linear_model from scikit-learn
from sklearn.linear_model import LinearRegression
Creat a Linear Regression Object using the constructor:
lm=LinearRegression()
Fitting  simple linear model
X = df[['highway-mpg']]
Y = df['price']
Yhat=im.predict(X)

Fitting a multiple linear model estimator
we can extract the for 4 predictor variables and store them in the variable z
z = df[['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']]
then train the model as before:
lm.fit(Z, df['price'])
we can also obtain a prediction
Yhat=lm.predict(X)

import seaborn as sns
sns.regplot(x='highway-mpg', y='price', data=df)
plt.ylim(0, )

import seaborn as sns
sns.residplot(df['highway-mpg'], df['price'])

import seaborn as sns
ax1=sns.distplot(df['price'], hist=False,  color='r', label='actual value')
sns.distplot(Yhat, hist=False, color='b', label='fitted values', ax=ax1)

Polynomial Regression
Calculate Polynomial of 3rd order
f=np.polyfit(x,y,3)
p=np.polyld(f)
print(p)

plolynomial regression with more than one dimension
the 'preprocessing' library in scikit-learn:
from sklearn.prepocessing import PolynomialFeatures
pr=PloynomialFeatures(degree=2, include_bias=False)
x_polly=pr.fit_transform(x[['horsepower', 'curb-weight']])
pr=PolynomialFeatures(degree=2)
pr.fit_transform([1,2}, include_bias=False)

plolynomial regression with more than one dimension
the 'preprocessing' library in scikit-learn:
from sklearn.preprocessing import PolynomialFeatures
pr=PolynomialFeatures(degree=2, include_bias=False)
x_polly=pr.fit_transform(x[['horsepower', 'curb-weight']])
**hada ghir bach t9adi bih scale hitach y9dro ykom=no l2ar9am kbira**
pre-processing
For example we can Normalize the each feature simultaneously:
from sklearn.preprocessing import StandardScaler
Scale=StandardScaler()
Scale.fit(x_data[['horsepower', 'highway-mpg']])
x-scale=SCALE.transform(x_data[['horsepower', 'highway-mpg']])
**we can simply our code by using pipeline libarary**

there are many steps to getting a prediction
Normalization, polynomial transform, linear regression the first two perfom transformation the last one perform prediction.
Pipelines
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import StandardScaler
from sklearn.pipeline import Pipeline
Input=[('polynomial', PolynomialFeature(degree=2)), ('Scale', StandardScaler()),.....('Model', LinearRegression())]
Pipeline constructor
pipe=Pipeline(Input)

we can train the pipeline object
Pipe.fit(df[['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']], y)
yhat=Pipe.predict(X[['horsepower', 'curb-weight', 'engine-size', 'highway-mpg']])
and we get the predicted value
