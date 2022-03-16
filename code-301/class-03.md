# Readings: Passing Functions as Props

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[React Docs - lists and keys](https://reactjs.org/docs/lists-and-keys.html)
* What does .map() return?
  * map is an array method that returns a new array populated with the same amount of data as the original array it pulled from. 
* If I want to loop through an array and display each value in JSX, how do I do that in React?
  * looks like you can loop through the data in an array then it will return a list item ```<li>``` for each item. JSX allows embedding any expression in curly braces, so you could inline the results from map().
  ```js
  const numbers = [1, 2, 3, 4, 5];
  const listItems = numbers.map((number) =>
  <li>{number}</li>
  ); 
  ```
* Each list item needs a unique __key__.
* What is the purpose of a key?
  * Keys help react identify which items have changed. They should be given to the elements inside the array and give the element a stable identity. Keys will only make sense in the context of the surrounding array. keys should be unique among siblings but don't need to be globally unique. 

[The Spread Operator](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
* What is the spread operator?
  * The spread operator is used for adding items to arrays or objects, it can also spread an array out into a functions arguments. 
* List 4 things that the spread operator can do.
  * it can do many things! It can copy an array, it can combine or concatenate arrays, it can add states to react, it can convert NodeList to an array, and more!
* Give an example of using the spread operator to combine two arrays.
  * an example is: 
  ```js 
  const = numArray = [1, 2, 3]
  const = strArray = ['one','two','three']
  const = numstrArray = [...numArray,...strArray]
  console.log(...numstrArray) // 1, 2, 3, 'one', 'two','three'
  ``` 

* Give an example of using the spread operator to add a new item to an array.
  * an example is
  ```js
  const fewFruit =['pear', 'apple', 'banana']
  const fewMoreFruit=['cherry','pineapple', ...fewFruit]
  console.log(fewMoreFruit) // Array(5)["cherry", "pineapple","pear","apple","banana"]
  ```
* Give an example of using the spread operator to combine two objects into one.
  * an example is
  ```js
  const objOne = {hello: 'hi'}
  const objTwo = {world: 'you'}
  const objThree = {...objOne,...objTwo, laugh: 'you silly'}
  const objFour = {...objOne, ...objTwo, laugh:()=>{console.log("you silly".repeat(5))}}
  objFour.laugh() // you sillyyou sillyyou sillyyou sillyyou silly
  ```

## Videos
[How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)

* In the video, what is the first step that the developer does to pass functions between components?
  * create objects, then use the map method to go through an array to generate the objects, then create a function where ever the state is that they're going to change. Pass in the object as a parameter into the function so it knows what to reference. Then you can use props from the objects. 
* In your own words, what does the increment function do?
  * the increment function takes a name from the array, loops through the array via map() method and updates the appropriate name once it finds the match. Once it finds the match, it adds 1 to the count within the object with the matching name. 
* How can you pass a method from a parent component into a child component? 
  * you create a key/value pair that will call {this.method}
* How does the child component invoke a method that was passed to it from a parent component?
  * call the method within the child component this.props.method(this.props.name)

## Things I want to know more about
I'm not sure I completely understand the map() method in conjunction with jsx and how it's different from vanilla js. I'd like to touch on this more. 
Like-wise I feel pretty unsure about the videos content, in theory it makes sense but the terminology and what is parent vs child component is kind of tripping me up. I think in this case repetition will be key. Just keep swimmin. 

## Bookmark/Skim
[React Tutorial through ‘Declaring a Winner’](https://reactjs.org/tutorial/tutorial.html)
[React Docs - Lifting State Up](https://reactjs.org/docs/lifting-state-up.html)
