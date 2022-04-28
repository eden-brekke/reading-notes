# Reading

[Dunder Methods](https://dbader.org/blog/python-dunder-methods)

Various dunder methods that unlock language features: 

* Initialization of new objects
* Object representation
* Enable iteration
* Operator overloading (comparison)
* Operator overloading (addition)
* Method invocation
* Context manager support (with statement)
* Dunder methods let you take behavior of built-in methods

dunder init initializes the class and takes care of the class attributes 

dunder repr is the string statement representations for your objects, kinda of for the devs rather than the users

dunder str is informal string statment representation of your objects, kind of for the users rather than the devs


to iterate over transactions there are: 

* len
* getitem
* reversed

operator overloading and comparing accounts use: 

* eq
* lt
* for merging: add


Callable python objects use:

* call

context manager support and with statement:

* enter
* exit




[Statistics - Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)

What is probability? 
Essentially: What is the chance of an event happening?
Statistics is gathering data on probablity and quantifying it. 

Central Limit Theorem lets us know that the average of many trials means will approach a true mean

three sigma rule (empirical rule) is an expression of how many of our observations fall within a certain distance of the mean

z-score is a calculation that answers "given a data point, how many standard deviations is it away from the mean"



## Videos

[Intro to Statistics](https://www.youtube.com/watch?v=MdHtK7CWpCQ)

He says "Statistics is a collection of procedures and principles for gaining information in order to make decisions when faced with uncertainty"  
Stats are so important that they can work in any field  

They can be used for 

* identifying risk factors for disease
* customzing spam detection
* establishing relationships between variables
* more

talks a lot about box plots
box plots are a box, with a median line and uncertainty bars (deviation and outliers)

probability distribution is an important aspect of statistics 

bayesian statistics and frequentists statistics
b. stats have varying parameters, fixed data, credible intervals, and the strength of priors
f. stats have fixed parameters, variable data, confidence interval and no priors


[AI Guru makes $238,800 with misleading paid course. doesn’t credit developers](https://www.youtube.com/watch?v=7jmBE4yPrOs)

This video is about  the guy from the above video
Basically what I got from this is don't mislead people   
Don't steal peoples codes   
If you use someone's code, then properly credit them   
Don't just git clone people's repos but fork instead so they know you've done so   

### Bookmark and Review

[Statistics Module](https://docs.python.org/3/library/statistics.html)