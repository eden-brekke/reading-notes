# Reading

Today's reading is about using the Random Module, doing Risk Analysis, proper test coverage and more on BigO notation. 

[How to use Random Module](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

The random module provides access to functions that support many operations typically it's used for generating random numbers.  

Functions the module contains: 

* Randint : Randit accepts two integers, a low and a high and returns one of the numbers between those parameters.  
* Random: mulitply by a number to generate a random number between 0 and that number  
* Choice: generate a random value from the sequence. (such as a list)
* Shuffle: shuffles the elements in list into a random order
* Randrange: randomly select element from range (start, stop, step)

heads or tails?  

```py 
import random
import itertools

outcomes = { 'heads':0,
              'tails': 0,
              }
sides = outcomes.keys()

for i in range(10000):
  outcomes[random.choice(sides)] += 1

print 'Heads:', outcomes['heads']
print 'Tails:', outcomes['tails']
```

[What is Risk Analysis](https://www.edureka.co/blog/risk-analysis-in-software-testing/)

At first I got a 503 error, so that was fun. :) 

Risk is: an unwanted incident.  
Risk Analysis is: the process of identifying the risks of an app/software that you build and prioritizing the testing of those risks.  

A list of possible risks you could encounter:  

* The use of new hardware
* Use of new technology
* use of new automation tool
* sequence of code
* availability of test resources for the application

Certain risks are unavoidable

* Time you allocated fro testing
* defect leakage due to complexity or size of application
* urgency from the clients to deliver the project
* incomplete requirements

Tackling the solution:

* Hold risk assessment review meeting
* Use max resources to work on high-risk areas
* create risk assessment database for future use
* identify and notice the risk magnitude indicator: high, medium and low
  * high means effect of risk would be high and non-tolerable (company might face losses)
  * medium is tolerable but not desirable (company may suffer financially but there is limited risk)
  * low is tolerable and there is little or no exposure or loss of finances  

Risk Identification:

* Business Risks: most common risk. Risk may come from your company or customer but not the project
* Testing Risks: you should be well acquainted with the platform you are working on along with the software testing tools being used
* Premature release risk: fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required
* software risk: risks associated with the software development process.

Three perspectives of risk assessment: effect, cause, likelihood

Effect: Identify a condition event or action and determine the impact.  
Cause: Initialize scanning the problem and think about the most probable reason behind the problem
Likelihood: Asses the probability that a requirement won't be satisfied

Perform Risk Analysis:

1. Search for the risk
2. Analyze the impact of each risk
3. measure for risk identified

[Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)

Test coverage talks about how extensively you test your code
some say you need 87% coverage, some say you need 100% coverage.  
100% coverage is fishy, aim for 80s and 90s  
Don't fall below 50%  
But high numbers don't necessarily mean much.  
Sufficiency is more about how and what you're testing rather than how much coverage you have  

## Videos

[Big O Notation](https://www.youtube.com/watch?v=v4cd1O4zkGw)

Her favorite topic... Big O (algorithmic efficiency)

company tested if they could send a huge file over the internet and pit it against a pigeon with a usb stick and the pigeon reigned supreme. Go birdy go!  

Transfering data over the internet takes longer depending on the amount of data. O(N) scales linearly with the amount of input  
The pigeon is an O(1) constant time with respect to the size  

if you have an array and you want to print a value in the array thats O(N) where N is the size of the array  
similarly if you want to print all the pairs in the array, it will print 5 and 2 as well as 2 and 5 meaning it's going to double print the values making this an O(N^2) where N is the size of the array again  


Four Important Rules of BigO

1. if you have two different steps in your algorithm you add up the steps. so if step one is  O(A) and step two is O(B) you really have O(A+B)
2. Drop constants so if you have two loops as your two steps O(N) + O(N) =  O(2N) its just O(N), drop the constant cause it still grows linearly
3. If you have different inputs you use different variables to represent them. O(a*b)
4. Drop non-dominant terms. first step O(N) second O(N^2) O(N+N^2) both of these will reduce down to O(N^2) since O(N^2) is what its going to drive how the runtime changes

### Bookmark and Review

[Python Random](https://docs.python.org/3/library/random.html)

### Further Reading

[What is Dependency Injection](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/)

* We won’t be covering this concept in depth until following class but it’s a big concept and needs some time to settle in.

* When class A uses some functionality of class B then class A has a dependency of class B

Three types of Dependency injection

1. Constructor injection: dependencies provided through class constructor
2. setter injection: client exposes setter method that the injector uses to inject the dependency
3. interface injection: the dependency provides an injector method that will inject the dependency into any client passed to it.

Dependency injections responsibility to: 

1. create the objects
2. know which classes require those objects
3. provide them all those objects

Benefits of DI

1. Helps in unit testing
2. boiler plate code is reduced, as initializing of dependencies is done by the injector component
3. extending applications becomes easier
4. helps to enable loose coupling, which is important in application programming

Disadvantages of DI

1. Bit complex to learn and if overused can lead to management issues and other problems
2. many compile time errors are pushed to run-time
3. dependency injection frameworks are implemented with reflection or dynamic programming. This can hinder use of IDE automation

