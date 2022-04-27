# Reading

[List Comprehensions](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

Python's comprehension features

Syntax:  
my_new_list = [expression for item in list]  
For the above code to work it needs:

1. The expression you'd like to carry out
2. The object that the expression will work on
3. the iterable list of objects to build our new list from

Notes about List Comprehensions:

* list comprehension methods are elegant ways to create/manage lists
* in python, list comprehensions are a more compact way of creating lists
* more flexible than for loops, list comprehension is usually faster than other methods

Create a list with range()
digits = [x for x in range(10)]  

Show the first letter for each word using python  
letters = [ name[0] for name in authors ]
print(letters)

basically it seems like you can use a lot of methods in this list comprehension things. Neat

## Things I'd like to know more about

If there are any disadvantages to using the list comprehensions in python?  
Advantages are that it's elegant and clean, but are there more maybe in the sense of BigO? 

## Audio

Listen (optional): [Debugging with PySnooper](https://www.pythonpodcast.com/pysnooper-python-debugging-episode-241/)

### Bookmark and Review

[Primer on Decorators](https://realpython.com/primer-on-python-decorators/)