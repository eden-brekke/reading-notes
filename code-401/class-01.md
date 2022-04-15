# Reading

[Pain and Suffering](https://codefellows.github.io/code-401-python-guide/curriculum/class-01/notes/pain_suffering)

The price of taking Code 401 which is 2 years worth of knowledge from a university is: pain :) 

We'll be pushed mentally.  
Have to think through problems that were just introduced to us.  
Will have to do self guided research.  

We'll be pushed emotionally.  
Confronted with our own lack of understanding and working past that.  

We'll be pushed physically.  

But this is not suffering because suffering is pain without purpose.  
This pain has a purpose! knowledge. 

During the 10 weeks consider these questions:  

1. What's your perspective?
2. Why are you doing this?
3. Do you want what comes at the end of this journey?
4. Are you doing this for you?

Don't forget to ask questions.  
Don't forget to research.  
Build your resources and community.  
Remember that you're here because you chose to invest in a different and better life.  

[Beginners Guide to Big O](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation)

Big O Notation is used in CS to describe performance and complexity of an algorithm.  
Describes worst-case scenario and can be used to describe execution time required/space used by an algorithm.  

O(1) describes an algorithm that will always execute at the same time regardless of size of input data set.  

O(N) describes an algorithm whose performance will grow linearly and in direct proportion to size of input data set.  

O(N2) describes an algorithm whose performance is directly proportional to square of size of input data set.  

O(2N) describes an algorithm whose growth doubles with each addition to the input data set.  

O(logN) Logarithms are tricky to explain, works by selecting the middle element of the data set(median essentially) and compares it against a target value.  



## Additional Resources

[Season 1, Episode 6, A friendly intro to Big O Notation](https://www.codenewbie.org/basecs/8)

They talked about Link Lists, Singly linked list, moving in one direction.  
Doubly link list that can move both directions.  
And Circular link list that don't have an end node pointing to null, instead it points back to the start.  

Big O evaluations how efficient something is.  
Talk about algorithms and how useful a data structure is  
How much time/memory does it take/need

Constant time is A+ run an algorithm and it doesn't matter how many things you're dealing with, always takes some amount of time/space  O(1)  
And example of this is adding to the top of a linked list  

Linear time is O(N) and that example if adding to the end of the linked list.  this is still an A- grade

O(N2) is quadratic time and is no good  





## Videos

[Names and Values in Python](https://www.youtube.com/watch?v=_AEJHKGk9ns)

Names refer to values (variables)  
Many names can refer to one value  
Names are reassigned independently  
x = 23 ... y = x ... x = 12 ... means y is still 23 while x is 12 now  

Values live until no references exist  
Assignment never copies data  

Immutable values can't alias  
Mutable values can alias  

References can be more than just names  
Lots of things are references  

* Object attributes 
* list elements 
* dict values and keys
* anything to the left side of an assignment  

Lots of things are also assignments  

Python is dynamically typed  
names have no types associated with them but they have scope  
values have no scope but do have a type  

### Bookmark and Review

[Awesome Python Environment](https://towardsdatascience.com/how-to-setup-an-awesome-python-environment-for-data-science-or-anything-else-35d358cc95d5)

[Python Module of the Week](https://pymotw.com/3/index.html)