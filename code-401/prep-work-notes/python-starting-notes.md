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


## Half way done! You got this :)

## More Types

The *none* object is used to represent the absence of a value 

it's similar to null in other programming languages

similar to other empty values (0 [] '') it registers as False  
and it will display as an empty string within the python console

The none object is returned by any function  that doesn't explicitly return anything else

```py
def some_func():
  print("Hi")

var = some_func()
print(var)
```

## Dictionaries 

dictionaries are data structures used to map arbitrary keys to values

lists can be thought of as dicitonaries with integer keys within a certain range 

dictionaries can be indexed in the same way as lists, using square brackets containing keys

```py
ages = {"Dave":24, "Mary":42, "John":58}
print(ages["Dave"])
print(ages["Mary"])
```
 
each element in a dictionary is represented by a key:value pair

trying to index a key that isnt part of the dictionary returns a *KeyError*

```py
primary = {
  "red": [255,0,0],
  "green":[0,255,0],
  "blue":[0,0,255],
}

print(primary["red"])
print(primary["yellow"]) # KeyError
```

only immutable objects can be used as keys to dictionaries

immutable objects are those that can't be changed

so far the only mutable objects we've seen are lists and dictionaries 

trying to use a mutable object as a dictionary key will cause a *TypeError*

```py
bad_dict = {
  [1,2,3]: "one two three", #type error
}
```

just like lists, dictionary keys can be assigned to different values 

however, unlike lists, a new dictionary key can also be assigned a value, not just ones that already exist 

```py
squares = {
  1:1,
  2:4,
  3:"error",
  4:16,
}

square[8] = 64
square[3] = 9
print(squares)
```

to determine whether a key is in a dictionary you can use *in* and *not in* just as you can for a list

```py
nums = {
  1: "one",
  2: "two",
  3: "three",
}
print(1 in nums)
print("three" in nums)
print(4 not in nums)
```

a useful dictionary method is "get" 
it does the same thing as indexing but if the key isnt found it returns another specified value

```py
pairs = {
  1: "apple",
  "orange": [2,3,4],
  True: False,
  None: "True",
}

print(pairs.get("orange"))
print(pairs.get(7)) # return none
print(pairs.get(12345, "not in dictionary")) #return not in dictionary
```

## Tuples

Tiples are very similar to lists, except that they are immutable (can't be changed)

and they are created using parentheses instead of square brackets

```py
words = ("spam","eggs","sausage",)
print(words[0])
words[1] = "cheese" # will through a TypeError since it's immutable
```

tuples can be created without the parentheses by just separating the values with commas

```py
my_tuple = "one","two","three"
print(my_tuple[0])
tpl=() # creates an empty tuple
```

tuples are faster than lists but cant be changed

## List Slices

list slices provide a more advanced way to retrieving values from a list

basic list slicing involves indexing a list with two colon-separated integers

this returns a new list containing all the values in the old list between the indices 

```py
squares = [0,1,4,9,16,25,36,49,64,81]
print(squares[2:6])
print(squares[3:8])
print(squares[0:1])
# these wont include the last indexes number in the print
```

if the first num in a slice is omitted it is taken to be the start of the list

if the second number is omitted it is taken to be the end

```py
squares = [0,1,4,9,16,25,36,49,64,81]
print(squares[:7]) # 0 1 4 9 26 25 36
print(squares[7:]) # 49 64 81
```

slicing can also be done on tuples

list slices can also have a third number, representing the step to include only alternate values in the slice

```py 
squares = [0,1,4,9,16,25,36,49,64,81]
print(squares[::2]) # 1 9 25 49 81
print(squares[2:8:3]) # 4 25
```

Negative values can be used in list slicing (and normal list indexing) when negative values are used for the first and second values in a slice (or a normal index) they count from the end of the list 

```py
squares = [0,1,4,9,16,25,36,49,64,81]
print(squares[1:-1])
```

if a negative value is used for the step  
the slice is done backwards  
using [::-1] as a slice is a common and idiomatic way to reverse a list 

## List Comprehensions 

List comprehensions are a useful way of quickly creating lists whose contents obey a simple rule 

```py
# a list comprehension
cubes = [i**3 from i in range(5)]
print(cubes)
```

i*2 for i in range(10) will APPARENTLY list all even numbers between 0 and 18 which makes no sense to me 
but I guess i * 2 means 10 * 2 = 20 and since the last number isnt included thats 0-18 but also only even numbers because of the 2..?

A list comprehension can also contain an if statement to enforce a condition on values in the list

```py
evens = [i**2 for i in range(10) if i**2 % 2 == 0]
print(evens)
```

Trying to create a list in a v extensive range will result in a *MemoryError* 

this code shows an example where the list comprehension runs out of memory 

```py
even = [2*i for i in range (10**100)]
```

## String Formatting

so far to combine strings and non-strings you've converted the non-strings to strings and added them

string formatting provides a more powerful way to embed non-strings within strings

string formatting uses a strings format method to substitute a number of arguments in the string

```py 
# string formatting
nums = [4,5,6]
msg = "Numbers : {0} {1} {2}". format(nums[0], nums[1], nums[2])
print(msg)
```

string formatting can also be done with named arguments 

```py
a = "{x}, {y}".format(x=5, y=12)
print(a)
```

## String Functions

pythong contains many built in functions 

join = join a list of strings with another string as a separator  
replace = replace on substring in a string with another  
startswith and endswith = determine if there is a substring at the start and end of a string  
lower and upper = to change the case of a string  
split = split a list of strings with a separator  

```py
print(", ".join(["spam", "eggs", "ham"]))

print("Hello ME".replace("ME", "world"))

print("This is a sentence.".startswith("This"))

print("This is a sentence.".endswith("sentence."))

print("This is a sentence.".upper())

print("AN ALL CAPS SENTENCE.".lower())

print("spam, eggs, ham".split(", "))
```

## Numeric Functions 

to find the maximum or minimum of some numbers in a list you can use max and min

to find the distance of number from 0 (absolute value) you can use abs

to round a num to a certain num of decimal places use round

to find the total of a list use sum

```py
print(min(1,2,3,4,0,2,1))
print(max[1,4,9,2,5,6,8])
print(abs(-99))
print(abs(42))
print(sum([1,2,3,4,5]))
```

## List functions 

conditional statements
all and any take a list as an argument and return True or all or any arguments evaluate to true (or false)

the function enumerate can be used to iterate through the values and indices of a list simultaneously

```py
nums = [55,44,33,22,11]

if all([i>5 for i in nums]):
  print("All larger than 5")

if any([i%2 == 0 for i in nums]):
  print("at least one is even)

for v in enumerate(nums):
  print(v)
```

## Test Analyzer

example projet showing a program that analyzes a sample file to find what percentage of the text each character occupies

this section shows how a file could be open and read

```py
filename = input("Enter a filename: ")

with open(filename) as f:
  text = f.read()

print(text)
```

this part of the program shows a function that counts how many times a character occurs in a string

```py
def count_char(text, char):
  count = 0
  for c in text:
    if c == char:
      count += 1
  return count
```

this func takes text of the file and one character as its arguments  
returning the num of times that char appears in the text 

next call it for the file

```py
filename = input("Enter a filename: ")
with open(filename) as f:
  text = f.read()

print(count_char(text, "r"))
```

the next part of the program finds what percentage of the text each character of the alphabet occupies

```py
for char in "abcdefghijklmnopqrstuvwxyz":
  perc = 100 * count_char(text, char)/len(text)
  print("{0}-{1}%".format(char, round(perc,2)))
```

so all together the program is:

```py
nums = [55,44,33,22,11]

if all([i>5 for i in nums]):
  print("All larger than 5")

if any([i%2 == 0 for i in nums]):
  print("at least one is even)

for v in enumerate(nums):
  print(v)
  
filename = input("Enter a filename: ")
with open(filename) as f:
  text = f.read()

print(count_char(text, "r"))

for char in "abcdefghijklmnopqrstuvwxyz":
  perc = 100 * count_char(text, char)/len(text)
  print("{0}-{1}%".format(char, round(perc,2)))
```

## Functional Programming 

a style of programming that is based around functions 

a key part of functional programming (higher-order functions)

higher-order functions take other functions as arguments or return them as results

```py
def apply_twice(func, arg):
  return func(func(arg))

def add_five(x):
  return x + 5

print(apply_twice(add_five, 10))
```

## Pure Functions 

functional programming seeks to use pure functions

pure functions have no side effects and return a value that depends only on their arguments 

this is how functions in math work: for example, the cos(x) will for the same value of x alawys return the same result 

pure function: 

```py
def pure_function(x,y):
  temp = x +2*y
  return temp/(2*x+y)
```

impure function:

```py
some_list = []

def impure(arg):
  some_list.append(arg)
```

Using pure functions has both advantages and disadvantages

pure functions are :

* easier to reason about and test
* more efficient. Once the function has been evaluated for an input, the result can be stored and referred to the next time the function of that input is needed, reducing the number of times the function is called. This is called *memorization*
* easier to run in parallel

The main disadvantage of using only pure functions is that they majorly complicate the task of I/O since this appears to inherently require side effects and they can be more difficult to write in some situations 

## Lambdas 

you can create an anonymous function using lambda syntax  
this approach is most commonly used when passing a simple func as an argument to another function

syntax is shown in the next example and consists of the lambda keyword follow by arguments a colon and the expression to evaluate/return

```py
def my_func(f, arg):
  return f(arg)

my_func(lambda x: 2*x*x, 5)
```


lambda functions arent as powerful as named functions

can only do things that require a single expression (single line of code)

```py
def polynomial(x):
  return x**2 + 5*x + 4
print(polynomial(-4))

print((lambda x: x**2 + 5*x + 4) (-4))
```

lambda can be assigned to variables and used like normal functions

```py
double = lambda x: x*2
print(double(7))
```


## map 

built in map and filter are useful for higher order functions that operate on lists (iterable objects too)

function map takes a function and an iterable as an argument and returns new iterable with function applied to each argument 

```py
def add_five(x):
  return x + 5

nums = [11, 22, 33, 44, 55]
results = list(map(add_five, nums))
print(results)
```

can also use lambda syntax

```py 
nums= [11,22,33,44,55]
results = list(map(lambda x: x+5, nums))
print(results)
```

filter filters iterable by removing items that don't match a predicate 

```py
nums = [11,22,33,44,55]
res = list(filter(lambda x: x%2==0, nums))
print(res)
```

like map the results need to explicitly be converted to list to print it

## generators

generators are a type of iterable, like lists or tuples

unlike lists, they dont allow indexing with arbitrary indices, but they can still be iterated through with for loops  
they can be created using functions and the yield statement

```py
def countdown():
  i=5
  while i > 0:
    yield i
    i -= 1

for i in countdown():
  print(i)
```

the yield statement is used to define a generator, replacing the return of a function to provide a result to its called without destroying local variables

due to the fact that they yield one item at a time, generators dont have the memory restrictions of lists, so they can be infinite

```py
def infinite_sevens():
  while True:
    yield 7

for i in infinite_sevens():
  print(i)
```

finite generators can be converted into lists by passing them as arguments to the list function

```py
def numbers(x):
  for i in range(x):
    if i % 2 == 0:
      yield i

print(list(numbers(11)))
```

## Decorators 

provide a way to modify functions using other functions

ideal when need to extend functionality of functions that you dont want to directly modify

```py
def decor(func):
  def wrap():
    print("==========")
    func()
    print("==========")
  return wrap

def print_text():
  print("hello")

decorated = decor(print_text)
decorated()
```


define decor func w/ single param func

inside decor define nested func: wrap

wrap prints string, calls func, prints string

decor returns wrap  
decoreated = decor(print_text)  
where print_text is func  
so string func string is printed when decorated is called

@my_dec will have the same effect as: my_func = my_dec(my_func)

## Recursion

Recursion is a very important concept in functional programming

the fundamental part of recursion is self-reference - function calling themselves

classic example is factorial function 

```py
def factorial(x):
  if x == 1:
    return 1
  else: 
    return x * factorial(x-1)

print(factorial(5))
```

base case acts as the exit condition of the recursion

recursive functions can be infinite, which occur when you forget to implement the base case

below is an incorrect version of the factorial function

has no base case so it runs until the interpreter runs out of memory and crashes

```py
def factorial(x):
  return x * factorial(x-1)
print(factorial(5))
```

recursion can also be indirect

one function can call a second, which calls the first, which calls the second, repeat.

```py
def is_even(x):
  if x == 0: 
    return True
  else: 
    return is_odd(x-1)

def is_odd(x):
  return not is_even(x)

print(is_odd(17))
print(is_even(23))
```

## Sets

sets are data structures, similar to lists or dictionaries 

they are created using curly braces or the set function

they share some functionality with lists 

such as the use of *in* to check whether they contain a particular item

```py
num_set = {1,2,3,4,5}
word_set = set(["spam","eggs","sausage"])

print(3 in num_set)
print("spam" not in word_set)
```

sets differ from lists in several ways, but share several list operations such as len

they are unordered, which means that they can't be indexed

they cannot contain duplicate elements

due to the way they're stored, it's faster to check whether an item is part of a set, rather than part of a list

instead of using append to add to a set, use add

the method remove removes element from a set, pop removes an arbitrary element

```py
nums = {1,2,1,3,1,4,5,6}
print(nums)
nums.add(-7)
nums.remove(3)
print(nums)
```

sets can be combined using math operations  
union operator | combines two sets  
intersection opertor & gets items that are in both sets  
difference operator - gets items in first but not second set  
symmetric difference operator ^ gets items in either set but not both  

## Data Structures 

Python supports: lists dictionaries, tuples, sets

When to use a dictionary:

* when you need a logical association between key:value pair
* when you need fast lookup for data, based on custom key
* when your data is being constantly modified. since they're mutable

When to use other types: 

* use lists if you have a collection of data that does not need random access.
  * try to choose lists when you need a simple, iterable collection that is modified frequently
* use a set if you need uniqueness for the elements
* use tuples when your data cannot change

Many times tuple are used in combination with dictionary: for example a tuple could be a key since it is immutable

## itertools

itertools is a standard library containing functions

one type of function is infinite iterators  
function count counts up infinitely from value  
function cycle infinitely iterates through an iterable 
repeat repeats an object either infinitely or specific number of times

```py
from itertools import count

for i in count(3):
  print(i)
  if i >= 11:
    break
```

many functions in itertool operate on iterables similar to map and filter  
takewhile - takes an item from interable while predicate function remains true  
chain - combines several iterables into one long one;  
accumulate - returns a running total of values in an iterable  

```py
from itertools import accumulate, takewhile

nums = list(accumulate(range(8)))
print(nums)
print(list(takewhile(lambda x: x<=6, nums)))
```

several combinatoric functions in itertool such as product and permutation

```py
from itertools import product, permutations

letters = ("A", "B")
print(list(product(letters, range(2))))
print(list(permutations(letters)))
```

## Classes

popular paradigm is object-oriented programming  
objects are created using classes which are the focal point of OOP

class describes what the object will be

```py
class Cat:
  def __init__(self, color, legs):
    self.color = color
    self.legs = legs

felix = Cat("ginger", 4)
rover = Cat("dog-colored",4)
stumpy = Cat("brown",3)
```

__init__ method is most important method in a class

called when object of the class is created

all methods have a self as first parameter 
self refers to the instance calling the method

instances of a class have attributes

Cat instance have attributes of color and legs and cab be accessed by putting a dot  
self.attribute


```py
class Cat:
  def __init__(self, color, legs):
    self.color = color
    self.legs = legs

felix = Cat("ginger", 4)
print(felix.color)
```

## Method

classes can have other methods defined to add functionality to them 

```py
class Dog: 
  def __init__(self, name, color):
    self.name = name
    self.color = color

  def bark(self):
    print("woof")

fido = Dog("Fido", "brown")
print(fido.name)
fido.bark()
```

classes can also have class attributes which are shared by all instances of the class

```py
class Dog: 
  legs = 4
  def __init__(self, name, color):
    self.name = name
    self.color = color

  def bark(self):
    print("woof")

fido = Dog("Fido", "brown")
print(fido.legs)
print(Dog.legs)
```

trying to access an attribute of an instance thaht isnt defined causes an AttributeError and applies when you call an undefined method

```py
class Rectangle:
  def __init__(self, width, height):
    self.width = width
    self.height = height

rect = Rectangle(7,8)
print(rect.color) # AttributeError
```

## Inheritance 

inheritance provides a way to share functionality between classes

```py
class Animal:
  def __init__(self, name, color):
    self.name = name
    self.color = color

class Cat(Animal):
  def purr(self):
    print("Purr..")

class Dog(Animal):
  def bark(self):
    print("woof")
  
fido = Dog("Fido","brown")
print(fido.color)
fido.bark()
```

class that inherit from another class are called subclass
and the class that was inherited from is called superclass

```py
class Wolf:
  def __init__(self,name,color):
    self.name = name
    self.color = color

  def bark(self):
    print("grrr")

class Dog(Wolf):
  def bark(self):
    print("woof")

husky = Dog("Max", "grey")
husky.bark()
```

inheritance can also be indirect, but circular inheritance is not possible

```py
class A: 
  def method(self):
    print("A method")

class B(A):
  def another_method(self):
    print("B method")

class C(B):
  def third_method(self):
    print("C method")

c = C()
c.method()
c.another_method()
c.third_method()
```

function super is an inheritance related function referring to the parent class

```py
class A:
  def spam(self):
    print(1)

class B(A):
  def spam(self):
    print(2)
    super().spam()

B().spam()
```

## Magic Methods

special methods with double underscores  
also known as dunders  
example: __init__

common use of them is operator overloading  
this means defining operators for custom classes that allow operators such as + and * to be used on them  
example: __add__ and +

```py
class Vector2D:
  def __init__(self, x,y):
    self.x = x
    self.y = y
  def __add__(self, other):
    return Vector2D(self.x + other.x, self.y + other.y)

first = Vector2D(5, 7)
second = Vector2D(3, 9)
result = first + second
print(result.x)
print(result.y)
```

the __add__ method allows for the definition of a custom behavior for the + operator in our class

all methods start and end with __

* sub for -
* mul for * 
* truediv for /
* floor div for //
* mod for % 
* pow for ** 
* and for &
* xor for ^ 
* or for |

so x + y would be x.__add__(y)
but if x hasn't implmeneted add and x and y are diff types then y.__radd__(x) can be called 
there are equivalent r methods for all methods above


```py
class SpecialString: 
  def __init__(self, cont):
    self.cont = cont
  
  def __truediv__(self, other):
    line = "=" * len(other.cont)
    return "\n".join([self.cont, line, other.cont])
  
spam = SpecialString("spam")
hello = SpecialString("hello")
print(spam/hello)
```

A() ^ B() will evaluate B().__rxor__(A()) so long as A doesnt implement any magic methods

Python provides some magic methods for comparisons too

* lt for <
* le for <=
* eq for ==
* ne for !=
* gt for >
* ge for >=

```py
class SpecialString:
  def __init__(self, cont):
    self.cont = cont

  def __gt__(self, other):
    for index in range(len(other.cont)+1):
      result = other.cont[:index] + ">" + self.cont
      result += ">" + other.cont[index:]
      print(result)

spam = SpecialString("spam")
eggs = SpecialString("eggs")
spam > eggs
```

more methods

* len for len()
* getitem for indexing
* setitem for assigning index
* delitem for deleting indexed value
* iter for iteration over objects
* contains for in

```py
class VagueList:
  def __init__(self, cont):
  self.cont = cont

  def __getitem__(self, index):
    return self.cont[index + random.randint(-1,1)]

  def __len__(self):
    return random.randit(0, len(self.cont)*2)

vague_list = VagueList(["A","B","C","D","E"])
print(len(vague_list))
print(len(vague_list))
print(vague_list[2])
print(vague_list[2])
```

above len() is overridden for the class VagueList to return a random number  
indexing function also returns a random item in a range from the list, based on the expression 

## Object Lifecycle 

the lifecycle of an object is made up of its creation, manipulation and destruction  
the first stage is the definition  
then instantiation  
then the object is ready for use

other code can interact with the object by calling functions on it and accessing its attributes, then it can be destroyed

when an object is destroyed, the memory allocated to it is freeee

destruction of an object occurs when its reference count reaches zero  
reference count is the number of variables and other elements that refer to an object  
if nothing is referring to it, nothing can interact with it and it can be deleted  

The del statement reduces the reference count of an object by one  
magic method ```__del__```

when an objects reference count reaches zero pythong automatically deletes it 

```py
a = 42 # create object
b = a # increase ref count
c = [a] # increase ref count again

del a # decrease ref count
b = 100 # decrease ref count
c[0] = -1 # decrease ref count
```


## Data Hiding

key part of OOP is encapsulation which involves packaging of related variables and functions into easy to use object  
data hiding states that implementation details of a class should be hidden and a clean standard interface be presented for those using the class 

weakly private methods and attributes have a single underscore at the beginning 

its only actual effect is tht from module_name import * wont import variables that start with a single underscore

```py
class Queue: 
  def __init__(self, contents):
    self._hiddenlist = list(contents)
  
  def push(self, value):
    self._hiddenlist.insert(0,value)
  
  def pop(self):
    return self._hiddenlist.pop(-1)
  
  def __repr__(self):
    return "Queue({})".format(self._hiddenlist)

queue = Queue([1,2,3])
print(queue)
queue.push(0)
print(queue)
queue.pop()
print(queue)
print(queue._hiddenlist)
```

in the code above, the attribute _hiddenlist is marked as private, but can still be accessed in the outside code 
__repr __ method is used for string rep of the instance

strongly private methods have double underscores  
purpose is to avoid bugs if there are subclasses that have methods or attributes with same name  

the method __privatemethod of class Spam could be accessed external with _Spam__privatemethod

```py
class Spam:
  __egg = 7
  def print_egg(self):
    print(self.__egg)

s = Spam()
s.print__egg()
print(s_Spam__egg)
print(s.__egg)
```

## Class Methods 

class methods are different, called by class which is passed to cls parameter of the method  
common use of these are factory methods which instantiate an instance of a class using diff parameters than those usually passed to the class constructor  
class methods are marked with a classmathod decorator

```py
class Rectangle: 
  def __init__(self, width, height):
    self.width = width
    self.height = height
  
  def calculate_area(self):
    return self.width * self.height
  
  @classmethod
  def new_square(cls, side_length):
    return cls(side_length, side_length)

square = Rectangle.new_square(5)
print(square.calculate_area())
```

new_square is a class method and is called on the class rather than on the instance of the class. returns a new object of the class cls

## Static methods

static methods are similar to class methods except they don't receive any additional arguments  
they are identical to normal functions that belong to a class  
they are marked with the staticmetho decorator

```py
class Pizza: 
  def __init__(self, toppings):
    self.toppings = toppings

  @staticmethod
  def validate_topping(topping):
    if topping == "pineapple":
      raise ValueError("No Pineapples")
    else:
      return True

ingredients = ["cheese", "onions", "spam"]
if all(Pizza.validate_topping(i) for i in ingredients):
  pizza = Pizza(ingredients)
```

static methods behave like plain functions, except for the fact that you can call them from an instance of the class 

## Properties 

properties provide a way of customizing access to instance attributes  
created by putting property decorator above a method  
properties make an attribute read-only

```py
class Pizza:
  def __init__(self, toppings):
    self.toppings = toppings
  
  @property
  def pineapple_allowed(self):
    return False

pizza = Pizza(["cheese","tomato"])
print(pizza.pineapple_allowed)
pizza.pineapple_allowed = True
```

properties can be set by defining setter/getter functions  
setter sets the corresponding property's value  
getter gets the value

```py
class Pizza: 
  def __init__(self, toppings):
    self.toppings = toppings
    self._pineapple_allowed = False

  @property
  def pineapple_allowed(self):
    return self._pineapple_allowed
  
  @pineapple_allowed.setter
  def pineapple_allowed(self, value):
    if value:
      password = input("enter password: ")
      if password == "Sw0rdf1sh!":
        self._pineapple_allowed = value
      else:
        raise ValueError("Alert! Intruder!")

pizza = Pizza(["cheese","tomato"])
print(pizza.pineapple_allowed)
pizza.pineapple_allowed = True
print(pizza.pineapple_allowed)
```

## a simple game

old fashioned text-based adventure game 

```py
def get_input():
  command = input(": ").split()
  verb_word = command[0]
  if verb_word in verb_dict:
    verb = verb_dict[verb_word]
  else: 
    print("Unknown verb {}". format(verb_word))
    return
  
  if len(command) >= 2:
    noun_word = command[1]
    print(verb(noun_word))
  else:
    print(verb("nothing"))
  
def say(noun):
  return 'You said "{}"'.format(noun)

verb_dict = {
  "say": say,
}

while True:
  get_input()

class GameObject:
  class_name = ""
  desc = ""
  objects = {}

  def __init__(self, name):
    self.name = name
    GameObject.objects[self.class_name] = self
  
  def get_desc(self):
    return self.class_name + "\n" + self.desc
  
class Goblin(GameObject):
  def __init__(self, name):
  self.class_name = "goblin"
  self.health = 3
  self._desc = "A cute creature"
  super().__init__(name)

  @property
  def desc(self):
    if self.health >=3:
      return self._desc
    elif self.health == 2:
      health_line = "it has a wound on its knee"
    elif self.health == 1:
      health_line = "its left arm has been cut off"
    elif self.health <=0:
      health_line = "its dead"
    return self._desc + "\n" + health_line
  
  @desc.setter
  def desc(self, value):
    self._desc = value

def hit(noun):
  if noun in GameObject.objects: 
    thing = GameObject.objects[noun]
    if type(thing) == Goblin:
      thing.health = thing.health - 1
      if thing.health <=0:
        msg = "yOu killed the goblin"
      else:
        msg = "ou hit the {}".format(thing.class_name)
  else: 
    msg = "There is no {} here.".format(noun)
  return msg

goblin = Goblin("Gobbly")

def examine(noun):
  if noun in GameObject.objects:
    return GameObject.objects[noun].get_desc()
  else: 
    return "There is no {} here.".format(noun)


```

## Regular Expressions

powerful tool for various kinds of string manipulation

domain specific language (DSL) that is present as a library  
two main tasks:

* verifying strings match a pattern
* performing substitutions in a string (such as changing american spellings to british ones)

can be accessed using the re module  
after defining an re the re.match function can be used to determine whether it matches at the beginning of the string

```py
import re
pattern = r"spam"

if re.match(pattern, "spamspamspam"):
  print("match")
else:
  print("no match")
```

other match patterns are  
re.search which finds a match of a pattern anywhere in the string  
re.findall which returns a list of all substrings that match a pattern

```py
import re
pattern = r"spam"

if re.match(pattern, "eggspamsausagespam"):
  print("match")
else:
  print("no match")

if re.search(patter, "eggspamsausagespam"):
  print("match")
else: 
  print("no match")

print(re.findall(pattern, "eggspamsausagespam"))
```

regex search returns an object  
group returns a string  
start and end return starting/ending position of the first match  
span returns the start and end positions of first match as a tuple

```py
import re

pattern=r"spam"
match = re.search(pattern, "eggspamsausage")
if match:
  print(match.group())
  print(match.start())
  print(match.end())
  print(match.span())
```

## Search and Replace

```py
re.sub(pattern, repl, string, count = 0)
```

```py
import re
str = "My name is David. Hi David"
pattern = r"David"
newstr = re.sub(pattern, "Amy", str)
print(newstr)
```

## Metacharacters
 
are what make re more powerful than normal string methods

first metacharacters : .(dot) which matches any character other than a new line 
the ^ matches start 
the $ matches end 

```py
import re 

pattern = r"^gr.y$"

if re.match(pattern, "grey"):
  print("Match 1")
if re.match(pattern, "gray"):
  print("Match 2")
if re.match(pattern, "blue"):
  print("Match 3")

if re.match(pattern, "stingray"):
  print("Match 4")
```

## Character Classes 

provide a way to match only one of the specific set of characters  
character class is created by putting the character it matches inside square brackets

```py
import re
pattern = r"[aeiou]"

if re.search(pattern, "grey"):
  print("Match 1")

if re.search(pattern, "qwertyuiop"):
  print("Match 2")

if re.search(pattern, "rhythm myths"):
  print("Match 3")
```

the pattern [aeiou] in the search function matches all strings that cointain any one of the characters defined

character classes can also match ranges of characters 
[a-z] any lower
[G-P] any upper from G to P
[0-9] any digit 
and multiple ranges can be included [A-Za-z]

```py
import re
pattern = r"[A-Z][A-Z][0-9]"

if re.search(pattern, "LS8"):
  print("Match 1")

if re.search(Patter, "E3"):
  print("Match 2")

if re.search(pattern, "1ab"):
  print("Match 3")
```

place a ^ at the start of a character class to inert it  
this causes it to match any character other than the ones included  

```py
import re
pattern = r"[^A-Z]"

if re.search(pattern, "this is all quiet"):
  print("Match1")

if re.search(pattern, "AbCdEfG123"):
  print("Match2")
  
if re.search(pattern, "THISISALLSHOUTING"):
  print("Match3")
```
  
more metacharacters are * + ? {and}

where * means zero or more reptitions 

```py
import re
pattern = r"egg(spam)*"

if re.match(pattern, "egg"):
  print("Match1")
  
if re.match(pattern, "eggspamspamegg"):
  print("Match2")
  
if re.match(pattern, "spam"):
  print("Match3")
```

and + is similar meaning one or more repeitions 

pattern = r"g+"

the ? means zero or one repetitions 

```py
import re
pattern = r"ice(-)?cream"

if re.match(pattern, "ice-cream"):
   print("Match1")

if re.match(pattern, "icecream"):
   print("Match2")

if re.match(pattern, "sausage"):
   print("Match3")

if re.match(pattern, "ice--ice"):
   print("Match4")
```

curly braces can be used to represent the number of repetitions between two num  
regex{x,y} means between x and y reps of something
so {0,1} means the same thing as ?
if first num is missing its taken to mean 0 and if second num is missing its taken as infinity  

## Groups

can be created by surrounding part of a re with parenths
this means a group can be given as an argument to metacharacters such as * and ?

```py
import re 
pattern = r"egg(spam)*"

if re.match(pattern, "egg"):
  print("Match 1")
if re.match(pattern, "eggspamspamspamegg"):
  print("Match 2")

if re.match(pattern, "spam"):
  print("Match 3")
```

contents of groups in match can be accessed using group()  
group() and group(0) return whole match 
group(n) returns nth group from left

```py
import re
pattern = r"a(bc)(de)(f(g)h)i"

match = re.match(papttern, "abcdefghijklmnop")
if match:
  print(match.group())
  print(match.group(0))
  print(match.group(1))
  print(match.group(2))
  print(match.groups())
```

named groups have format (?P<name>...) where name is the name of the group and ... is the content  
non-capturing groups have the format (?:...) are not accessible by group method so they can be added to an existing re qithout breaking the numbering

```py
import re
pattern = r"(?P<first>abc)(?:def)(ghi)"

match = re.match(pattern, "abcdefghi")
if match:
  print(match.group("first"))
  print(match.groups())
```


important metacharacter is | and it means or

```py
import re 
pattern = r"gr(a|e)y"

match = re.match(pattern, "gray")
if match:
  print("Match 1")

match = re.match(pattern, "grey")
if match: 
  print("Match 2")

match = re.match(pattern, "griy")
if match: 
  print("Match 3")
```

## Special sequence 

they are written as a backslash followed by another character

```py
import re
pattern=r"(.+) \1"

match = re.match(pattern, "word word")
if match:
  print("match 1")

match = re.match(pattern, "?! ?!")
if match:
  print("match 2")

match = re.match(pattern, "abc cde")
if match:
  print("match 3")
```

more special sequence are 

* \d for digits 
* \s for whitespace
* \w for word character 

the above sequences can be written with uppercase which means the opposite so \D would mean anything but a digit

```py
import re
pattern = r"(\D+\d)"

match = re.match(pattern, "Hi 999!")
if match:
  print("match 1")

match = re.match(pattern, "1, 23, 465!")
if match:
  print("match 2")

match = re.match(pattern, " ! $?")
if match:
  print("match 3")
```

special sequence \A for beginning of string \Z to match end of string \b to match an empty string between \w and \W or \w and the beginning or end of a string (boundary between words) \B matches empty string elsewhere

```py
import re
pattern = r"\b(cat)\b"
match = re.search(pattern, "the cat sat")
if match:
  print("match 1")

match = re.search(pattern, "we s>cat<tered?")
if match:
  print("match 2")

match = re.search(pattern, "We scattered")
if match:
  print("match 3")
```

## zen of python

The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

## PEP

python enhancement proposal 

- modules should have short, all-lowercase names;
- class names should be in the CapWords style;
- most variables and function names should be lowercase_with_underscores;
- constants (variables that never change value) should be CAPS_WITH_UNDERSCORES;
- names that would clash with Python keywords (such as 'class' or 'if') should have a trailing underscore
- lines shouldn't be longer than 80 characters;
- 'from module import *' should be avoided;
- there should only be one statement per line.

python allows to have function with varying num of arguments

*args as a func param enables you to pass an arbitrary num   
so you could pass *args then when you invoke pass any number of args  

*args inside a function is accessed as the tuple of args

**kwards stands for keyword arguments allows you to handle arguments that have not defined in advance

tuple unpacking allows you to assign each item in an iterable to a variable
 
a variable that is prefaced with an asterisk takes all values from the interable that are left over from other variables

ternary operator  
provides funationality of is statement with less code 

else statement is most commonly used along with if
but it can also follow a for or while loop which give it diff meanings

else statements can also be used with try/except statements 

__ main __  ensure it wont be run if the file is imported

Django: The most frequently used web framework written in Python, Django powers websites that include Instagram and Disqus. It has many useful features, and whatever features it lacks are covered by extension packages.
