# Reading

Todays reading is about classes and objects in Python which will make our code more clean and reusable. As well as how to think recursively which will make our code more efficient.

[Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)

Objects are an bunch of variables and functions rolled into one entity.  
Objects get their variables and functions from classes  
Classes are a template to create your objects  

Example: 

```py
class MyClass: 
  variable = "stuff"

  def function(self):
    print("Message inside the class")
  
my_obj = MyClass()

my_obj.variable
my_obj.function()
```

you can create multiple objects with the same class.  
but each object contains independent copies of the variables defined within the class.  

Init()  
the __ init __() function is a special function that is called when the class is being initiated.  
it's used for assigning values in a class  

[Thinking Recursively](https://realpython.com/python-thinking-recursively/)

* Optional: Naive Recursion is Naive section and beyond

The easiest way to make a big scary problem less scary is by breaking it down piece by piece  
This is essentially what recursiveness does  

If a current problem represents a simple case then solve it.  
If not, then divide it into many subproblems and solve them.  

A recursive function is a function defined in terms of itself via self-referential expressions  
Behind the scenes each recursive call adds a stack to the call stack until it reaches the base case.  

Maintaining State:  
To maintain state during recursion you have to either:

* threat the state through each recursive call so that the current state is part of the current call's execution context 
* keep the state in global scope

Recursive Data Structures in Python:  
A data structure can be called recursive if it can be defined in terms of a smaller version of itself.  
A list is a recursive data structure, so are sets, tree, dictionaries and more. 

Example of a list as a recursive data type:

1. Start with an empty list, then generate the list by recursively applying the attach_head function
2. Recursion can also be seen as self-referential function compositions. Apply a function to an argument then pass the result as an argument to a second application of the same function and so on. 
[Pytest Fixtures and Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)

### Bookmark and Review

[Pytest Fixtures](https://docs.pytest.org/en/latest/explanation/fixtures.html)