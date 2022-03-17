# Readings: Putting it all together
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[React Docs - Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

* What is the single responsibility principle and how does it apply to components?
  * it says that components should ideally one perform one function, and if the file ends up growing it should be decomposed into smaller subcomponents 
* What does it mean to build a ‘static’ version of your application?
  * This means to build your app without any interactivity. 
* Once you have a static application, what do you need to add?
  * Once you have the static app you'll need to add the interactivity, making your app dynamic. 
* What are the three questions you can ask to determine if something is state?
  * Is it passed from the parent as props? if so its not a state
  * does it change overtime? if yes then probably a state, if no then probably a prop
  * can you compute it based on other state or props in the component? if yes then it's not a state 
* How can you identify where state needs to live?
  * the state needs to live where it can be changed and passed down to children, so most likely in the parent component 

[Higher-Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)

* What is a “higher-order function”?
  * higher order functions are functions that operate on other functions, by taking them as arguments or by returning them
* Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?
  * its a function handing in "n" as an argument and returning a boolean if you run the function and pass in another argument. 
* Explain how either map or reduce operates, with regards to higher-order functions.
  * I think an example of this is when we pass in the callback functions in our challenges while using map 


## Things I want to know more about
I want to know more about the reduce function and maybe a better explanation of how the map/reduce methods work in regards to higher order functions. 