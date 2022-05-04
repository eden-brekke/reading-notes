# Reading

[How to Run Linear Regression in Python](https://bigdata-madesimple.com/how-to-run-linear-regression-in-python-scikit-learn/)
  * NOTE: Since this demo was published scikit-learn has been updated. The train_test_split function is now imported from sklearn.model_selection

Scikit-learn - is a Python module for machine learning.  It contains functions for: 
* Regression
* Classification
* Clustering
* Model Selection
* Dimensionality

Scikit.linear_model contains "methods intended for regression in which the target value is expected to be a linear combination of the input variables"

Step 1:
```python
%matplotlib inline

import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt
import sklearn
```

Important functions while fitting linear regression model:
* lm.fit -> fits a linear model
* lm.predict() -> Predict Y using the linear model with estimated coefficients
* lm.score() -> return the coefficient of determination (R^2). *measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model* 

Conclusion of what was covered in the article:
* Explored the dataset and then renamed the column names
* explored the data set using .DESCR, where the goal was to predict the housing proces using the given features
* Used Scikit learn to fit linear regression to the entire data set and calculated the mean squared error
* Made a train-test split and calculated the mean squared error for the training data and test data
* Plotted the residuals for the training and test datasets

## Additional Resources

[Linear Regression in Python](https://realpython.com/linear-regression-in-python/)

## Videos

[Introduction to Simple Linear Regressions](https://www.youtube.com/watch?v=KsVBBJRb9TE)

### Bookmark and Review

[Train & Test Splits](https://towardsdatascience.com/train-test-split-and-cross-validation-in-python-80b61beca4b6)

[What is Linear Regression](https://www.statisticssolutions.com/free-resources/directory-of-statistical-analyses/what-is-linear-regression/)