# Readings: Pythonisms

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

## [Dunder Methods](https://dbader.org/blog/python-dunder-methods)
In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.  
 “dunder methods”, a short form of “double under.”
 
 -  Object Initialization: `__init__`
	- Right upon starting my class I already need a special method. To construct account objects from the `Account` class I need a constructor which in Python is the `__init__` dunder
- Object Representation: `__str__` `__repr__`
	1.  **`__repr__`**: The “official” string representation of an object. This is how you would make an object of the class. The goal of `__repr__` is to be unambiguous.
	2.  **`__str__`**: The “informal” or nicely printable string representation of an object. 
- Iteration: `__len__`, `__getitem__`, `__reversed__`
- Operator Overloading for Comparing Accounts: `__eq__`, `__lt__`
- Operator Overloading for Merging Accounts: `__add__`
- Callable Python Objects: `__call__`
- Context Manager Support and the `With` Statement: `__enter__`, `__exit__`

## [Iterators](https://dbader.org/blog/python-iterators)
-   Iterators provide a sequence interface to Python objects that’s memory efficient and considered Pythonic. Behold the beauty of the _for-in_ loop!
-   To support iteration an object needs to implement the _iterator protocol_ by providing the `__iter__` and `__next__` dunder methods.
-   Class-based iterators are only one way to write iterable objects in Python. Also consider generators and generator expression

## [Generators](https://dbader.org/blog/python-generators)
-   Generator functions are syntactic sugar for writing objects that support the iterator protocol. Generators abstract away much of the boilerplate code needed when writing class-based iterators.
-   The `yield` statement allows you to temporarily suspend execution of a generator function and to pass back values from it.
-   Generators start raising `StopIteration` exceptions after control flow leaves the generator function by any means other than a `yield` statement.

## Videos

(Optional): [What are Generators](https://realpython.com/lessons/what-are-python-generators/)

## Bookmark and Review

[Decorators](https://realpython.com/primer-on-python-decorators/)