# Solo Learn Python Course

### Strings

``` python
print("Python is fun!")
print('Always look on the bright side of life')
```

Can use either double or single quotes. 
Similar to JavaScrip the escape character is a backslash

``` python
print('Brian\'s mother: He\'s not an angel. He\'s a very naughty boy!')
```

### New Lines

\n will create a new line within a string text 

``` python
print('One\nTwo\nThree')
```

In similar fashion \t represents a tab. 
If you use three quotes """ that will also create new lines automatically within text 

``` python 
print("""this 
is a
multiline
text.""")
```

### Concatenation 

As with integers and floats (numbers and decimals) strings can be added <br>
Even if your string contains numbers, they'll still be added as strings <br> 
If you try to add a string to a number it will produce an error

``` python
print("Spam" + 'eggs')
print("2" + "2")
```

### String Operations 

Strings can be multiplied by integers. <br>
This will produce a repeated version of the original string <br>
The order of the string and integer doesn't matter, but best practice is that the string comes first. <br>
strings cannot be multiplied by other strings, and cannot be multiplied by floats <br>

``` python
print("spam"+3)
print(4+'2')
```

### Variables 

A variable allows you to store a value by assigning it a name. <br>
that name can then be referred to later in the program <br>

``` python
user = "James"
```

Certain restrictions apply when naming python variables <br>
Letters, numbers and underscores are the only characters that can be used within a name <br>
They cannot start with a number either <br>

``` python
this_is_a_normal_name = 7
123abc = 7 (will result in a syntax error)
```

You can use variables to perform operations just as you can with strings <br>

``` python
x = 7 
print(x)
print(x + 3)
print(x)
``` 

variables can be reassigned any number of times to change the value <br>
in python variables don't have specific types, so you can assign a string to a variable and later assign an integer to the same variable <br>
though this is not best practice

``` python
x = 123.456
print(x)

x = "this is a string"
print(x+"!")
```

### Getting User Input

To get input from a user in python, you can use the input function <br>
for example, a game can ask for the user's name and age as an input an duse them in the game <br>
the input function prompts the user for input, and returns what they enter as a string 

``` python
x = input()
print(x)
```

The input statement needs to be followed by parentheses <br>
you can provide a string to input between the () producing a prompt message

``` python
name = input('Enter your name: ")
print("Hello, " + name)
```

Let's assume we want the age of a user <br>
using input will return string <br>
so to get input as an integer we can use int() in conjunction with input to convert the input from a string to an integer <br>

``` python
age = int(input())
print(age)
```

Similarly to convert from a number to a string you can use str() <br>
This can be useful if you need a number in your string concatenation <br>
Also if you need a float you can use float()

``` python
age = 42
print("His age is " + str(age))
```

### In-Place Operators 

In-place operators allow you to write code like 'x=x +3' more concisely as 'x+=3'  <br>
The same thing is possible with other operators such as -,*,/ and % as well <br>

``` python 
x = 2 
print(x)

x += 3
print(x)
```

These operators can be used on types other than numbers, as well as strings <br>
can be used for any operators can be used for any numerical operation (+,-,*,/,%,**,//)

``` python 
x="spam"
print(x)

x += "eggs"
print(x)
```

### Walrus Operator

The Walrus Operator := allows you to assign values to variables within an expression, including variables that don't exist yet <br>
So you could take an integer from the user and assign it to a variable num and output it <br>

``` python 
num = int(input())
print(num)
```

Walrus operator accomplishes these operations at once:

``` python
print(num:=int(input()))
``` 

## Booleans

another "type" in python is a boolean type <br>
there are two boolean values: true and false <br>
they can be created by comparing values, for example by using the == operator <br>

``` python 
my_boolean = True
print(my_boolean)
True

print(2 == 3)
False

print('hello' == 'hello')
True
```

### Comparison 

Another comparison operator is != not equal, will return a boolean, true if they are not equal and false if they are equal <br>

``` python 
print(1 != 1)
False
print('eleven' != 'seven')
True
print(2 != 10)
True
```

Python also has operators that determine whether one number (float or integer) is greater than or smaller than another. <br>
These operators are > and < respectively <br>

``` python 
print(7 > 5)
True
print( 10< 10)
False
```
The greater than or equal to and smaller than or equal operators  >= and <= <br>
Same as strict greater than and small than operators but they return true when comparing equal numbers

``` python
print(7<=8)
True
print(9 >= 9.0)
True
```
Greater than and smaller than operators can be used to compare strings lexicographically (the alphabetical order of words is based on alphabetical order of their components letters) <br>

``` python
print("Annie" > "Andy")
True
```

Since the first two characters from Annie and Andy are compared they are equal, the second two n and n are equal so the third n and d aren't equal, they get compared and because n has a greater alphabetical order value than d Annie is greater than Andy. <br>

## If Statements 

You can use if statements to run code if a certain condition holds. <br>
If an expression evaluates true, some statements are carried out <br>

``` python
if expression :
  statements
```
Python uses indentation to delimit blocks of code. sometimes indentation is mandatory. <br>

``` python
if 10 > 5: 
  print("10 is greater than 5")

print("Program ended")
```

To perform more complex checks, if statements can be nested, one inside the other. <br>
This means that the inner if statement is the statement part of the outer one. <br>
this is one way to see whether multiple conditions are satisfied <br>

``` python 
num = 12
if num > 5:
  print("Bigger than 5")
  if num <=47
    print("Between 5 and 47")
```

### else statements

The if statement allows you to check a condition and run some statements, if the condition is true. <br>
the else statement can be used to run some statements when the condition of the if returns false <br>
you must put a colon after the else keyword <br>

``` python
x = 4
if x == 5:
  print("yes")
else: 
  print("no")
```

Every if condition block can have only one else statement <br>
in order to make multiple checks you can chain if and else statements <br>

``` python
num = 3 
if num == 1:
  print("one")
else:
  if num == 2:
    print("two")
  else:
    if num == 3:
      print("three")
    else:
      print("something else")
```

### Elif statements 

Multiple if/else statements make the code long and unreadable <br>
elif is a way to shortcut this chaining <br>

``` python
num = 3 
if num == 1:
  print('one')
elif num == 2:
  print('two')
elif num == 3:
  print('three')
else: 
  print('something else')
``` 


### Boolean Logic
used to make more complicated conditions for if statements that rely on more than one condition <br>
there are: and, or, and not <br>
and takes two arguments and evaluates as true if both are true. <br>

``` python
print(1 == 1 and 2 == 2)
True
print(1 == 1 and 2 == 3)
False
print(1!=1 and 2==2)
False
print(2<1 and 3 >6)
False
```

the or operator also takes two arguments. <br>
It evaluates True if either or both are true and false if both are false <br>

``` python
print(1==1 or 2==2)
True
print(1==1 or 2==3)
True
print(1!=1 or 2==2)
True
print(2<1 or 3>6)
False
```

Unlike the other operators not will only take one argument and inverts it. <br>
The result of not True is false and not False goes to true

``` python
print(not 1==1)
False
print(not 1>7)
True
```

### Operator precedence 
operator precedence is very important, and is an extension of the mathematical idea of order of operations. <br>
== has a higher precedence than or <br>
Python's order of operations is the same as that of normal mathematics: parentheses first, then exponentiation, then multiplication/division, and then addition/subtraction <br>

``` python
print(False == False or True)
True
print(False == (False or True))
False
print((False == False)or True)
True
```

### Chaining Multiple Conditions 

You can chain multiple conditional statements in an if statement using the boolean operator <br>

``` python
grade == 88
if (grade >= 70 and grade <=100):
  print("passed!")
```

## Lists
Lists are used to store items <br>
Lists can be created using square brackets and commas to separate the items <br>
You can access each item in the list by calling it's index, which will start at 0 and count up. <br>

``` python
words = ["hello","world","!"]
print(words[0])
print(words[1])
print(words[2])
```

you can create an empty list to populate later 

``` python
empty_list = []
print(empty_list)
```

Its common practice for lists to hold one data type but it can hold multiple data types <br>
lists can be nested within lists <br>

``` python
number = 3
things = ["string", 0, [1,2,number], 4.56]
print(things[1])
print(things[2])
print(things[2][2])
```

nested lists can be used to represent 2D grids such as matrices <br>
Can be used in cases where you need to store data in row-column format. <br>

``` python
m = [
  [1, 2, 3],
  [4, 5, 6]
  ]
print(m[1][2])
```

Some types, such as strings, can be indexed like lists. <br>
spaces also will have an index <br>

``` python
str = "hello world!"
print(str[6])
```

Items at a certain index in a list can be reassigned <br>

``` python
nums = [7,7,7,7,7]
nums[2] = 5
print(nums)
```

Lists can be added and multiplied in the same way as strings <br>

``` python
nums = [1,2,3]
print(nums + [4,5,6])
print(nums * 3)
```


To check if an item is in a list, the in operator can be used<br>
it returns true if the item occurs one or more times in the list and false if it doesn't <br>

``` python
words = ["spam", "eggs", "spam", "sausage"]
print("spam" in words)
print("egg" in words)
print("tomato" in words)
```

to check if an item isn't in a list you can use the not operator <br>

``` python
nums = [1,2,3]
print(not 4 in nums)
print(4 not in nums)
print(not 3 in nums)
print(3 not in nums)
```

The append method adds an item to the end of an existing list. <br>

``` python 
nums = [1, 2, 3]
nums.append(4)
print(nums)
```

To get the number of items in a list you can use the len function <br>
Unlike the index of items, len doesn't start with 0, so len will return the number 5 for the list below, not 4 <br>

``` python
nums = [1, 3, 5, 2, 4]
print(len(nums))
```

The insert method is similar to append, except it allows you to choose the position you insert into instead of it automating to the end of the list <br>

```python
words = ["Python", "fun"]
index = 1
words.insert(index, "is")
print(words)
```

the index method finds the first occurrence of a list item and returns the index <br>
if the item isn't in a list it raises a ValueError <br>

``` python
letters = ['p', 'q','r','s','p','u']
print(letters.index('r'))
print(letters.index('p'))
print(letters.index('z'))
```

A few more useful functions and methods for lists:
* max(list) returns list item with max value
* min(list) returns list item with min value
* list.count(item) returns a count of how many times an item occurs in a list
* list.remove(item) removes an object from a list
* list.reverse(): reverses items in a list

## while loops

a while loop is used to repeat a block of code multiple times

```py
i=1
while i <=5: 
  print(i)
  i = i + 1

print("finished")
```

You can use multiple statements in the while loop

```py
x=1 
while x < 10:
  if x%2 == 0:
    print(str(x)+" is even")
  else:
    print(str(x)+" is odd)
  x += 1
```
str(x) is converting the number x into a string so that it can be used for the concatenation

### break

to end a while loop prematurely the break statement can be used

```py
i = 0 
while True:
  print(i)
  i = i + 1
  if i >=5:
    print('breaking')
    break

  print('finished')
```

while True is a short and easy way to make an infinite loop
an infinite while loop can be used to continuously take user input. for example, you are making a calculator and need numbers from the user to add and stop when the user enters stop
in this case the break statement can be used to end the infinite loop when the user input equals 'stop'

### Continue

another statement that can be used within loops is *continue*

unlike break, continue jumps back to the top of the loop rather than stopping it
basically it stops the current iteration and continues with the next

```py
i = 0 
while i < 5
  i += 1
  if i == 3:
    print('Skipping 3')
    continue
  print(i)
```

## for loops

the for loop is used to iterate over a given sequence such as lists or strings

```py
words =['hello','world','spam','eggs']
for word in words: 
  print(word + '!')
```

the for loop can be used to iterate over loops

```py
str = "testing for loops"
count = 0 

for x in str:
  if(x=='t'):
    count +=1
  
print(count)
```

## for vs while

both for and while loops can be used to execute a code for multiple times
its common to use the for loop when the number of iterations is fixed
the while loop is used in cases when the iteration isn't known and depends on some calculations and conditions within the code

## Range
the range() function returns a sequence of numbers
by default it starts at 0 and increments by 1 and stops before a specified number

```py
numbers=list(range(10))
print(numbers)
```

if range is called with one argument it'll produce an object ith values from 0 to that argument
if its called with two arguments, it produces values from the first to the second

```py
numbers = list(range(3,8))
print(numbers)
print(range(20)==range(0,20))
```
the second argument will not be included in the range 

range can have a third argument which determines the interval of the sequence produced also called the step 

```py
numbers = list(range(5,20,2))
print(numbers)
```
we can also create list of decreasing numbers, using a negative number as the third argument for example list(range(20,5,-2))

for loop is commonly used to repeat some code a certain number of times, this is done by combining for loops with range objects

```py
for i in range(5):
  print('hello')
```

you dont need to call list on the range object when it is used in a for loop because it isn't being indexed

## FizzBuzz

FizzBuzz is a well known programming assignment asked during interviews
the given code solves the fizzbuzz problem and uses the words solo and learn instead

it takes an input n and outputs the numbers from 1 to n
for each multiple of 3 print "solo" instead of the number
for each multiple of 5 print "learn" instead of the number
for numbers which are multiples of both 3 and 5 output "SoloLearn"
you need to change the code to skip the even numbers so that the logic only applies to odd numbers in the range

```py
n = int(input())

for x in range(1,n):
  if x%2 == 0:
    continue
  if x % 3 == 0 and x % 5 == 0:
    print('SoloLearn")
  elif x % 3 == 0:
    print("solo")
  elif x % 5 == 0:
    print("learn")
  else:
    print(x)
```

# Next Module Functions and Modules

## Reusing Code

Code ruse is v important in coding 
increasing code size makes it harder to maintain

for large programming project to be successful it's essential to abide by the Dont Repeat Yourself (dry) principle

## Function

any statement that consists of the a word followed by parentheses is a function call

examples:

```py
print("hello world")
range(2,20)
str(12)
range(10,20,3)
```

in addition to using predefined functions you can create your own functions by using the def statement

```py
def my_func():
  print("spam")
  print("spam")
  print("spam")

my_func()
```
you must define functions before they are called, in the same way that you must assign variables before using them

```py
hello()

def hello():
  print("hello")
```

## arguments

a lot of functions take arguments 

```py
def print_with_exclamation(word):
  print(word + "!")

print_with_exclamation("spam")
print_with_exclamation("eggs")
print_with_exclamation("python")
```

you can define functions with more than one argument; separate them with commas 

```py
def print_sum_twice(x,y):
  print(x+y)
  print(x+y)

print_sum_twice(5,8)
```

function arguments can be used as variables inside the function definition 
but they can't be referenced outside of the functions definition

```py
def function(variable):
  variable += 1
  print(variable)

function(7)
print(variable)
```

this code above will throw an error because the variable is defined inside the function and can be reference only there

## returning from functions

certain functions, such as int or str, return a value that can be used later. 

```py
def max(x,y):
  if x>=y:
    return x
  else:
    return y
  
print(max(4,7))
z=max(8,5)
print(z)
```

Once you return a value from a function it immediately stops being executed
meaning any code after the return statement wont happen

```py
def add_numbers(x,y):
  total = x + y
  return total
  print("this wont be printed")

print(add_numbers(4,5))
```

## Comments and Docstrings

Comments are annotations to code used to make it easier to understand
they dont affect the code

```py
x=365
y=7
# this is a comment

print (x %y) # find the remainder
# print(x//y)
# another comment
```

Docstrings serve a similar purpose to comments,  as they are designed to explain code
they are more specific and have a different syntax
they are created by putting multiline string containing explanation of the function below the functions first line

```py
def shout(word):
  """
  Print a word with an 
  exclamation mark following it.
  """
  print(word + "!")

shout("spam")
```

docstrings are retained throughout the runtime of the program
allowing the programmer to inspect these comments at run time

although they are created differently from normal variables functions are just like any other kind of value
they can be assigned and reassigned to variables and later reference by those names

```py
def multiply(x,y):
  return x * y
a=4
b=7
operation = multiply
print(operations(a,b))
```

Functions can also be used as arguments of other functions

```py
def add(x,y):
  return x + y

def do_twice(func, x, y):
  return func(func(x,y), func(x,y))

a=5
b=10

print(do_twice(add, a, b))
```

## Modules

Modules are pieces of code that other people have written to fulfill common tasks such as generating random numbers, performing mathematical operations

the basic way to use a module is to add import module-name at the top of your code 
then using module_name.var to access functions and values with the name var in the module

```py
import random

for i in range(5):
  value = random.randint(1,6)
  print(value)
```

the code uses the randint function defined in the random module to print 5 random numbers in the range of 1,6

there is another kind of import that can be used if you only need certain functions from a module
these take the form from module_name import var and then var can be used as if it were defined normally in your code

```py
from math import pi

print(pi)
```

use a comma separated list to import multiple objects 

```py
from math import pi, sqrt
```

* will import all objects from module
but this is generally discouraged because it confuses variablesin your code with variables in the external module

trying to import a module that isnt available will cause an importError

```py 
import some_module
```

you can import a module or object under a different name using the *as* keyword 
this is mainly used when a module or object has a long or confusing name

```py
from math import sqrt as square_root
print(square_root(100))
```

there are three main types of modules in python  
those you write yourself  
those you install from external sources  
and those that are preinstalled with python  
the last type is called the standard library and contain useful modules  
some are: 

* string
* re
* datetime
* math
* random
* os
* multiprocessing
* subprocess
* socket
* email
* json
* doctest
* unitest
* pdb
* argparse
* sys

some tasks that can be done: 

* string parsing
* data serialization
* testing 
* debugging
* manipulating dates, emails, command line arguments and more

## The standard library

some modules in the standard library are written in python and some are written in C  
most are available on all platform but some are windows/unix specific

Many third party python modules are stored on the python package index (PyPI)  
the nest way to install these is using a program called pip  
this comes installed by default with modern distributions of python  
if you dont have it, its easy to install online  
Once you have it, installing libraries from PyPI is easy  
look up the name of the library you want to install and go to the command line and enter *pip install library_name*  
using pip is the standard way of installing lobraries on most operating systems

## Exceptions

exceptions happen when something goes wrong due to inccorect code or input  
when an exception occurs the program immediately stops

```py
num1=7
num2=0
print(num1/num2)
``` 

will throw an error because youre trying to divide by zero

Different exceptions are raised for different reasons
common exceptions:

* ImportError: an import fails
* IndexError: a list is indexed with an out-of-range number
* NameError: an unknown variable is used 
* SyntaxError: the code can't be parsed properly
* TypeError: a function is called on a value of an inappropriate type
* ValueError: a function is called on a value of the correct type, but with an inappropriate value

## Exception Handling

to handle exceptions and to call code when an exception occurs you can use try/except statement  
the try block contains code that might throw an exception  
if that exception occurs the code in the try block stops being executed, and the code in the except block is run  
if no error occurs the code in the except block wont run 

```py
try
  num1 = 7 
  num2 = 0
  print(num1/num2)
  print("dont calculating")
except ZeroDivisionError:
  print("an error occured")
  print("due to zero division")
```

A try statement can have multiple different except blocks to handle different exceptions 

multiple exceptions can also be put into a single except block using parentheses

```py
try:
  variable =10
  print(variable + "hello")
  print(variable/2)
except ZeroDivisionError:
  print("divided by zero")
except(ValueError, TypeError):
  print("Error occurred")
```

an except statement without any exception specified will catch all errors  
these should be used sparingly as they can catch unexpected errors and  hide programming mistakes

```py
try:
  word = "spam"
  print(word/0)
except:
  print("an error occurred")
```

finally  
to ensure some code runs no matter what errors occur, you can use a finally statement  
the finally statement is placed at the bottom of a try/except statement  
code within a finally statement always run after execution of the code in the try and possibly in the except blocks

```py
try: 
  print("Hello")
  print(1/0)
except ZeroDivisionError:
  print("Divided  by zero")
finally: 
  print("this code will run no matter what")
```

code in a finally statement even runs if an uncaught exception occurs

```py
try: 
  print(1)
  print(10/0)
except ZeroDivisionError:
  print(unknown_var)
finally: 
  print("this code will run last")
```

## Raising Exceptions

you can raise exceptions by using the raise statement

```py
print(1)
raise ValueError
print(2)
```

Exceptions can be raised with arguments that give detail about them

```py
name = "123"
raise NameError("Invalid name!")
```

In except blocks the raise statement can be used without arguments to reraise whatever exception occurred

```py
try:
  num = 5/0
except: 
  print('an error occurred')
  raise 
```

## Assertions

an assertion is a sanity-check that you can turn on or turn off when you have finished testing the program

an expression is tested and if the result comes up false an exception is raised

assertions are carried out through use of the assert statement

```py
print(1)
assert 2+2 == 4
print(2)
assert 1+1 == 3
print(3)
```

assert can take a second argument that is passed to the AssertionError raised if the assertion fails

```py
temp = -10
assert (temp >= 0), "Colder than absolute zero!"
```


## Opening Files

You can use python to read and write the contents of files

text files are the easiest to manipulate

before a file can be edited it must be opened using the open function

```py
myfile = open("filename.txt")
```

you can specify the mode used to open a file by applying a second argument to the open function

sending r meaning open in read only (default)  
sending w means write mode to rewrite the contents of a file  
sending a means append mode to add new content to the end of a file  
adding b to a mode opens it in binary mode which is used for non-text files  

```py
# write mode
open("filename.txt", "w")

# read mode
open("filename.txt", "r")
open("filename.txt")

# binary write mode
open("filename.txt", "wb")
```

once a file has been opened and used you should close it

this is done with the close method on the file object

```py
file = open("filename.txt", "w")
# do stuff to the file
file.close()
```

## Reading File

the content of a file that has been opened in text mode can be read using the read method 

```py 
file = open("filename.txt", "r")
cont = file.read()
print(cont)
file.close()
```

to read only a certain amount of a file you can provide a number as an argument to the read function, this determines the number of bytes that should be read

you can make more calls to read on the same file object to read more of the file byte by byte 

with no arguments, read returns the rest of the file

```py
file = open("filename.txt", "r")
print(file.read(16))
print(file.read(4))
print(file.read(4))
print(file.read())
file.close()
```

after all contents in a file have been read, any attempts to read further from that file will return an empty string

because you are trying to read from the end of the file

```py
file = open("filename.txt", "r")
file.read()
print("Re-reading")
print(file.read())
print("Finished")
file.close()
```

results in:  
>>>
Re-reading

Finished
>>>

to retrieve each line in a file you can use the readlines method to retun a list in which each element is a line in the file

```py
file = open("filename.txt","r")
print(file.readlines())
file.close()
```

results in:
['Line 1 text \n', 'line 2 text \n', 'line 3 text']

## Writing Files

to write to files you use the write method, which writes a string to the file

```py
file = open("newfile.txt","w")
file.write("This has been written to a file")
file.close()

file = open("newfile.txt","r")
print(file.read())
file.close()
```

when a file is opened in write mode the files existing content is deleted

```py
file = open("newfile.txt","r")
print("reading Initial contents)
print(file.read())
print("Finished")
file.close()

file = open("newfile.txt","w")
file.write("Some new text")
file.close()

file = open("newfile.txt","r")
print("Reading new contents")
print(file.read())
print("finished")
file.close()
```

the write method returns the number of bytes written into a file if successful

```py
msg = "Hello"
file = open("newfile.txt","w")
amount_written = file.write(msg)
print(amount_written)
file.close()
```

it is good practice to avoid wasting resources by making sure that files are always closed after they have been used.  
one way of doing this is to use the try and finally statements  

```py 
try: 
  f = open("filename.txt")
  print(f.read())
finally:
  f.close()
```

an alternative way of doing this is using *with* statements 

this creates a temporary variable (often called f) which is only accessible in the indented block of the with statement

```py
with open("filename.txt") as f:
  print(f.read())
```

