# Implementation: Linked Lists

To turn in your reading “Reply” to this discussion by teaching something that you learned. Then review what one of your classmates learned, and leave a comment.

Some ideas for how you might want to teach:

* Use an analogy
* Explain a detail in depth
* Use WHY, WHAT, HOW structure
* Tutorial / walk through an example
* Write a quiz
* Create a vocabulary/definition list
* Write a cheat sheet
* Create a diagram / visualization / cartoon of a topic
* Anthropomorphize the concepts, and write a  conversation between them
* Build a map of the information
* Construct a fill-in-the-blank worksheet for the topic

## Resources

* Read and save for reference: [Big O: Analysis of Algorithm Efficiency](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html) (Up through the section titled “Linear Complexity Growth”)
Hello! I decided to do a little fill in the blank worksheet for Big O notation since I have been struggling a bit with the concept!

* Big O is evaluated based off which two factors? ___Running Time___ and  ___Memory Space___
* Big O's role in algorithm efficiency is to describe the ___Worst Case_______ of efficiency an algorithm can have when performing it's job. 
* What are the four(4) key Areas for analysis for Big O?
	1._____Input Size________________
	2._____Units of Measurement________________
	3._____Orders of Growth________________
	4._____Best Case, Worst Case, and Average Case________________

* Which of the four key areas of analysis refers to the number of parameters, and how much space each parameter takes up within a program? _____Input Size_________

* Which of the four key areas of analysis quantifies the Running Time and Memory Space of the function? _____Units of Measurement_______

* Running time considers which Three(3) measurements of time?
	1. ______time in miliseconds from the start to end of a function____
	2. ____number of operations that are executed______
	3. ____Number of Basic operations executed______
* Memory space considers which Four(4) sources of memory usage?
	1. ____amount of space needed to hold the code______
	2. ____amount of space needed to hold input data______
	3. ____amount of space needed for the output data______
	4. ____amount of space needed to hold working space during calculations______

* Which of the four key areas of analysis describes the overall efficiency by representing the increase of running time and memory space? _____orders of growth_______

* Constant complexity can be represented as O(_1__)? (Stretch: An example of this is __returning the sum of two numbers_____)
* Logarithmic complexity can be represented as O(_...n-1__)?(Stretch: An example of this is ___searching for a value in a sorted array____)
* Linear Complexity can be represented as O(__n_)?(Stretch: An example of this is ____loop through an array and create a sum of their values___)
* Linearithmic Complexity can be represented as O(_lgn__)?(Stretch: An example of this is ____search through an array of sorted arrays___)
* Quadratic Complexity can be represented as O(__n^2_)?(Stretch: An example of this is _____sort through an array and loop through the values__)
* Cubic Complexity can be represented as O(_n^3__)?(Stretch: An example of this is ____nested loops___)
* Exponential Complexity can be represented as O(_log__)? (Stretch: An example of this is __fibonacci_____)
* Factorial Complexity can be represented as O(_n!__)? (Stretch: An example of this is ___calculate every possible arrangement of cards in a deck____)

* When something is described as: 'The efficiency for the worst possible input size of n' it's called the ____worst case_____ and the notation used for it is Big __O___
* When something is described as: 'The efficiency for the best possible input size of n' it's called the ____best case____ and the notation used for it is Big _Omega____
* Whe something is described as: 'The efficiency for the "typical" or "random" input size of n' it's called the __average case______ and the notation used for it is Big __Theta___


* Read: [Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

Terminology: 
* Linked List - data structure that contains nodes that links/points to the next node in a list 
* Singly and Doubly - refers to the number of references a node has, singly meaning one reference pointing to the next, and doubly meaning two references pointing to the previous and next nodes 
* Node - Individual items/links that live in a linked list
* Next - each node has a property called next. This property contains the reference to the next node
* Head - the starter (first) node in a linked list
* Current - the node that's currently being referenced


* Read: [What’s a Linked List, Anyway pt1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)
* Read: [What’s a Linked List, Anyway pt2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

In terms of Linked Lists there are two major types of BigO at play, O(1) (adding to the end of a linked list) and O(N) (adding to the beginning of a linked list) where Big O(1) being constant is faster, it doesn't care how many "books are in the stack" it will still take the same amount of time to add the next book to the end of the list. Big O(N) cares a bit more about how many "books are in the stack" and the efficiency lowers as more books(N) are added. 
