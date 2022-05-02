# Reading

[Pandas in 10](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)

A short introduction to Pandas, gear for new users! 
You can see more complex recipes in the Cookbook

```python
In [1]: import numpy as np
In [2]: import pandas as pd
```

#### Object creation
Creating a series by passing a list of values, letting pandas create a default integer index: 
```python
In [3]: s = pd.Series([1,3,5, np.nan, 6, 8])
In [4]: s
Out[4]:
0    1.0
1    3.0
2    5.0
3    NaN
4    6.0
5    8.0
dtype: float64
```

Creating a DataFrame: This can be done by passing an array as shown below or by passing a dictionary of objects

pass a np array with the datetime index and labeled columns: 

```python
In [5]: dates = pd.date_range("20130101", periods=6)

In [6]: dates
Out[6]: 
DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
               '2013-01-05', '2013-01-06'],
              dtype='datetime64[ns]', freq='D')

In [7]: df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))

In [8]: df
Out[8]: 
                   A         B         C         D
2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
2013-01-02  1.212112 -0.173215  0.119209 -1.044236
2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
2013-01-04  0.721555 -0.706771 -1.039575  0.271860
2013-01-05 -0.424972  0.567020  0.276232 -1.087401
2013-01-06 -0.673690  0.113648 -1.478427  0.524988
```

* NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column 
* `describe()` shows a quick statistic summary of your data:

#### Selection
* Getting - setting via [] which slices the rows	
* Selection By Label 
* Selection by position
* Boolean Indexing
* Setting

* Pandas primarily uses the value np.nan to represent missing data
	* dropna - drop any rows that have missing data
	* fillna - dill any rows that have missing data
	* isna - get boolean mask where values are nan
	

Operations:
* stats
* apply
* histogramming
* string methods

Merge: 
* concat
* join

Grouping:
* splitting: the data into groups based on some criteria
* applying: a function to each group independently
* combining: the results into a data structure

Reshaping:
* stack
* pivot tables 

This was a LOT of information overload. I'm not sure I totally understand it, but I'm excited to dive in! 

## Additional Resources

[Pandas - Getting Started](https://pandas.pydata.org/pandas-docs/stable/getting_started/intro_tutorials/index.html)

[Real Python - Pandas Tutorials](https://realpython.com/learning-paths/pandas-data-science/)

## Videos

[What is Pandas](https://www.youtube.com/watch?v=dcqPhpY7tWk&t=391s)

### Bookmark and Review

[Master Pandas](https://towardsdatascience.com/be-a-more-efficient-data-scientist-today-master-pandas-with-this-guide-ea362d27386)