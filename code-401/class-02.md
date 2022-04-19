# Reading

Why does this matter? Recursion is a fun new way to make our code cleaner and solves some problems that we've encountered and solved through iteration in a fun new way. So Fresh. So Clean.


[In Tests We Trust - TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

Unit testing are pieces of code to exercise the input, output and behavior of the code.  
Test driven development (TDD) is where you write thinking about the tests you'll run first.  

The example they give is "input Ana (name) Output female (gender) so write a test that checks if the name Ana is given it should return female. 

```py 
def test_should_return_female_when_name_is_from_female():
  detector = GenderDetector()
  expected_gender = detector.run('Ana')
  assert expected_gender == 'female'
```

Tests should be given names that are descriptive about what is expected and what is tested.

A test file name should follow the same name of a module name.  
So if the module is gender.py then the test name should be test_gender.py  

Convention widely used is AAA:  

* Arrange: organize data needed (input)  
* Act: execute code being tested (exercise behavior)  
* Assert: check if result (output) is the same as expected  

TDD the Cycle:  

* Write unit test and make it fail
* Write feature and make it pass  
*  Refactor the Code: first version doesn't need to be beautiful it can be changed  

Takeaways:  

* Greatest advantage about TDD is to craft the software design first
* Code will be more reliable: after a change you can run your tests and be in peace  
* Beginning may be hard, you just need practice  

[If name equals main](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)

Before executing code the python interpreters read source files and define variables  
If the interpreter is running the module as the main program it'll set the __name __ variable to have a value of " __ main __ " and if it's imported from another module it'll be set to the modules name.  

Advantages: 

* every python module has its name defined and if its main, it implies the module is being run standalone by the user and we can do corresponding actions
* if you import this script as a module in another script, the name is set to the name of that module 
* python files can act as either reusable modules, or as standalone programs
* if name == main is used to execute some code only if the file was run directly and not imported 



[Recursion](https://www.geeksforgeeks.org/recursion/)
  * Or the recursion video

  What is Recursion? 
 
 Recursion is where a function calls itself either directly or indirectly.  
 Using recursive algorithm, certain problems can be solved with ease.  

 Mathematical Interpretations: 

 ```py
 f(n)=1+2+3+.....+n
 ```

 What is the base condition in recursion?  
 In a recursive program, the solution is provided and the solution of the bigger problem is expressed in terms of smaller problems  

```js
int fact(int n)
{
  if(n < = 1 ) //base case
    return 1;
  else
    return n*fact(n-1);
}
```

How a particular problem is solved using recursion?  
The idea is to represent a problem in terms of one or more smaller problems, and add more base conditions that stop the recursion.  

Why Stack Overflow error occurs in recursion?  
If the base case isn't reached (or not defined) then the stack overflow problem may arise.  

What is the difference between direct and indirect recursion?  
Function is called direct recursive if it calls the same function.  
Function is called indirect recursive if it calls another function and the other function calls the first function directly or indirectly.  

What is the difference between tailed and non-tailed recursion?  
Recursive function is tail recursive when recursive call is the last thing executed by the function.  

How is memory allocated to different functions in recursion?  
When any function is called from main() it get some memory allocated to it on the stack.  
A recursive function calls itself and the memory for the called function is added on top of the memory allocated to calling the function.  

What are the disadvantages of recursive programming over iterative programming?  
They have the same problem-solving powers, and both can be written as the other.  
Recursive program has greater space requirements, because they remain in the stack until the base case is reached.  

What are the advantages of recursive programming over iterative programming?  
Recursion provides a clean and simple way to write code. 


## Videos

[What on Earth is Recursion](https://www.youtube.com/watch?v=Mv9NEXX1VHc)
  * Or the recursion reading

### Optional: 

[Python Modules and Packages Companion Video](https://realpython.com/courses/python-modules-packages/)

### Bookmark and Review

[Google for Education: Python Lists](https://developers.google.com/edu/python/lists)

[Google for Education: Python Strings](https://developers.google.com/edu/python/strings)

[Python Modules and Packages](https://realpython.com/python-modules-packages/)

[Pytest Documentation](https://docs.pytest.org/en/latest/)

[PyTest Tutorial](https://www.guru99.com/pytest-tutorial.html) Up to section Running tests in parallel