# Readings: Functional Programming
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

* What is functional programming?
  * this is a programming paradigm that treats computation as an evaluation of math and avoids changing-state and mutable data.
* What is a pure function and how do we know if something is a pure function?
  * the strict definition of purity is that it returns the same result if given the same arguments, and it doesn't cause any observable side effects. It wont use a global object, it must only use what it's passed in the parameters
* What are the benefits of a pure function?
  * makes the code easier to test. 
* What is immutability?
  * unchanging over time, or unable to be changed. state can't be changed after its creation. to handle mutability in iterations you use recursion
* What is Referential transparency?
  * if a function consistently yields the same results from the same input it's referentially transparent. in other words: pure functions + immutable data = referential transparency

## Videos
[Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)

* What is a module?
  * split code up into logical module(another js file), different module for different functionality of code. similar to components in react
* What does the word ‘require’ do?
  * if you want to bring a module (js file) to function on another file. require('./path/to/module') (don't need js on end)
* How do we bring another module into the file the we are working in?
  * use require to bring in the module you want to use, then inside the module with the functionality, you need to specify what parts you want to make available 
* What do we have to do to make a module available?
  * module.exports = theFunctionYouWantAvailable; then set theFunctionYouWantAvailable = to the require statement in the module you're passing the functionality to.

## Things I want to know more about
this might be for another time but I'm pretty curious about adding a cache to our backend servers, the modularity of separating functionality within files in the server made me think that adding a cache may be the next step we should take.