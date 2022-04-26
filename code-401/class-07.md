# Reading

* NOTE This is a long reading. The portion to make sure you cover is on global and nonlocal keywords. You can skim the rest.

[Python Scope](https://realpython.com/python-scope-legb-rule/)

LEGB rule.  
Local, enclosing, global, and built-in  

This tutorial covers:

* What scopes are and how they work in python
* Why it's important to know about python scope
* What the LEGB rule is and how python uses it to resolve names
* How to modify the standard behavior of python scope using global and nonlocal
* what scope-related tools python offer and how to use them

global keywords:  
is the top-most scope in the program  
python scope contains all of the names that you define at the top level  
Names in that scope are visible from everywhere  

nonlocal keywords:  
enclosing is another word for nonlocal.  
it's a special scope only existing for nested functions  
if the local scope is an inner or nested function then the enclosing scope is the scope of the outer function  
this scope contains names that you define in the enclosing function  
the names in the enclosing scope are visible from the code of the inner and enclosing functions  

global and nonlocal are two keywords that allow you to modify the content of global and nonlocal names  

the global statement  
with this statement you can define a list of names that are going to be treated as global names  

the nonlocal statement 
similarly to global names, nonlocal names can be accessed from inner functions, but not assigned or updated.  
to modify them you must use the nonlocal statement.  
with the nonlocal statement you can define a list of names that are going to be treated as nonlocal  
you cannot use nonlocal outside of a nested or enclosed function  

## Videos

* NOTE* The repeated Big O content is intentional. This is a big concept and worth hearing about from multiple presenters. TIP: watch on faster speed if you like.

[Don’t be CONFUSED by BIG O notation anymore!](https://www.youtube.com/watch?v=5Uqawfl0VHQ)

BigO time complexity  
space complexity  
all it really means is how long it takes to do something  
how much memory it takes up when you do the program.  

Why is it necessary?  
A way of comparing algorithms with each other.  
How will the algorithm perform when you start throwing data at it  

As the amount of data increase, how does the algorithm respond?  

Big(O) gives the worst scenario  
It's important for things such as a plane flying or the patient monitoring system is able to handle everything. So worst case is ideal.

Most common computational complexity:
* O(1) constant running time: ideal
* O(log n) logarithmic running time: scales on the time scale really slowly
* O(N) linear running time: acceptable performance
* O(N logN) log linear running time: not super ideal
* O(N^k) polynomial running time: super not ideal


### Bookmark and Review

[Rolling Dice Examples](https://artofproblemsolving.com/wiki/index.php/Basic_Programming_With_Python#Program_Example_1_3)