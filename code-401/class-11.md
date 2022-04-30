# Reading

[What is Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)
  * Just read the overview page, what you really want is the video on that page.
JupyterLab is a next gen web-based user interface for Project Jupyter

JupyterLab enables you to work with Jupyter notebooks, text editors terminals and custom components.

* Code consoles provide transient scratch pads to run code interactively.
* Kernel-backed documents enable code in any text file to be run interactively
* Notebook cell outputs can be mirror into their own tab
* JupyterLab will eventually replace classic Jupyter Notebooks

[Numpy Tutorial](https://www.dataquest.io/blog/numpy-tutorial-python/)
NumPy is a commonly used Python data analysis package
Using NumPy can speed up your workflow and interface with other packages in python that use NumPy under the hood 

All code blocks will be taken directly from the tutorial
Example Code for the tutorial: 
```python
"fixed acidity";"volatile acidity";"citric acid";"residual sugar";"chlorides";"free sulfur dioxide";"total sulfur dioxide";"density";"pH";"sulphates";"alcohol";"quality"
7.4;0.7;0;1.9;0.076;11;34;0.9978;3.51;0.56;9.4;5
7.8;0.88;0;2.6;0.098;25;67;0.9968;3.2;0.68;9.8;5
```
* ssv - semicolon separated values, this is the format that the tutorial data is presented in
	* each record is separated by a semicolon, and rows are separated by a new line

```python
import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))
```

Import the csv library, open the file, pass the keyword delimiter to ensure the records are split on the ; character

```python
print(wines[:3])
```

print the first three rows
 ```python
[['fixed acidity', 'volatile acidity', 'citric acid', 'residual sugar', 'chlorides', 'free sulfur dioxide', 'total sulfur dioxide', 'density', 'pH', 'sulphates', 'alcohol', 'quality'], ['7.4', '0.7', '0', '1.9', '0.076', '11', '34', '0.9978', '3.51', '0.56', '9.4', '5'], ['7.8', '0.88', '0', '2.6', '0.098', '25', '67', '0.9968', '3.2', '0.68', '9.8', '5']]
```

```python
qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)
```
Extract the last element from each row
convert each element to a float
assign all elements to the list "qualities"
and divide sum of elements by total elements to get the mean

#### Create NumPy array
```python
import csv
with open("winequality-red.csv", 'r') as f:
    wines = list(csv.reader(f, delimiter=";"))
import numpy as np
wines = np.array(wines[1:], dtype=np.float)
```
Import NumPy package
pass list of wines into array function
It seems like a lot of the operations in NumPy are pretty intuitive to how we've done operations in the past, with minimal or no syntax changes 

#### NumPy array methods
* numpy.ndarray.mean - finds the mean of an array
* numpy.ndarray.std - finds the standard deviation of an array
* numpy.ndarray.min - finds the minimum value in an array
* numpy.ndarray.max - finds the maximum value in an array

[Handy link to NumPy Cheat Sheet](https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf)

## Videos

  * Watch the video linked inside What is is Jupyter Lab reading
Basic categories:
* Text, code consoles and terminals
	* Includes synatx highlighting and configurable indentation
		* select kernal and create code console
* common formats
	* all popular img formats are supported as standalone files and in notebooks
	* Can view pdf's easily and html and tex
	* csv are viewed easily
	* json files can be editted
	* vega can be rendered
* jupyter notebook
	* two modes, command and edit 
		* command navigates and changes cells frame work
			* y to code and m to markdown
		* enter to edit currently active sell
--- 
> block quote :D

shift + enter will run the code 
changing a variable later will change the variable earlier if you re-execute the code



### Bookmark and Review

[Numpy Arrays](https://www.tutorialspoint.com/numpy/index.htm)