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

