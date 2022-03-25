# Readings: In memory storage
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[Understanding the JavaScript Call Stack](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4)

* What is a ‘call’?
  * the invocation of a function is to "call" the function
* How many ‘calls’ can happen at once?
  * one at a time
* What does LIFO mean?
  * LIFO stands for Last in First out, its a principle to temporarily store and manage function calls. The last function to be added to the stack will be the first one returned 
* Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.
  * push --> [  ] --> pop
  *          [  ]
  *          [  ]
  *          [  ]
  * think the example they used is: 
  ```js 
  function firstFunction (){
    console.log("Hello from firstFunction");
  }
  function secondFunction () {
    firstFunction();
    console.log("The end from secondFunction");
  }
  secondFunction();
  ```
  * Where the output would show: 
    1. Hello from firstFunction
    2. The end from SecondFunction 
* What causes a Stack Overflow?
  * A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. which will throw an error eventually of "maximum call size exceeded"

[JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

* What is a ‘refrence error’?
  * thrown most often when you try to use a variable that hasn't been declared yet
* What is a ‘syntax error’?
  * occurs when you have something that can't be parsed in terms of syntax, like missing a semicolon :)
* What is a ‘range error’?
  *  when trying to reference something like an empty array by it's length (or an array with length less than what you're trying to reference by)
* What is a ‘type error’?
  * when the type of data you're using is incompatible with what you're trying to use it with
* What is a breakpoint?
  * breakpoint is used in the console to put a pause on the code so you can see exactly whats happening in that moment 
* What does the word ‘debugger’ do in your code?
  * debugger is a way you can achieve the breakpoint by inputting it into your code

## Additional Resources
[JavaScript errors reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors) <br>

## Things I want to know more about