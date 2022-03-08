# Readings: Introduction to React and Components
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[Component-Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)

1. What is a “component”?
2. What are the characteristics of a component?
3. What are the advantages of using component-based architecture?

[What is Props and How to Use it in React](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0)

1. What is “props” short for?
2. How are props used in React?
3. What is the flow of props?

## Bookmark/Skim
[React Tutorial through ‘Passing Data Through Props’](https://reactjs.org/tutorial/tutorial.html)
[React Docs - Hello world](https://reactjs.org/docs/hello-world.html)
[React Docs - Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)
[React Docs - Rendering elements](https://reactjs.org/docs/rendering-elements.html)
[React Docs - Components and props](https://reactjs.org/docs/components-and-props.html)

## Assignment Instructions
Read for understanding the assigned resources for this class. Also skim and bookmark the additional resources provided. Prepare an entry for your Readings Notes Repository that answers each and every question presented above.

Make a section in your notes titled ## Things I want to know more about, and anytime a question arises in your mind, or something catches your curiosity, write it down under this heading.

## Things I want to know more about 


```
New Reading
```

# Readings and Resources: ES6 Classes

Below you will find some reading material, code samples, and some additional resources that will help you to better understand ES6 Classes

Watch the [Shred Talk: ES6 Classes](https://www.youtube.com/watch?v=9Yc5J3Ap9-4)
Review the [Demo Code](https://codefellows.github.io/code-301-guide/curriculum/prework/classes/DEMO.html)
Complete the [Assignment](https://codefellows.github.io/code-301-guide/curriculum/prework/classes/LAB.html)

## Objects and Inheritance

JavaScript objects use prototype-based inheritance. Its design is logically similar (but different in implementation) from class inheritance in strictly Object Oriented Programming languages like Java and C#. <br>

It can be loosely described by saying that when methods or properties are attached to object’s prototype they become available for use on that object and its descendants, but not directly attached to them.<br>

When you use class and extends keywords internally JavaScript will still use prototype-based inheritance. It just simplifies the syntax (this is often called “Syntactic Sugar”). While classes are easier to use, it’s still very important to understand how prototype-based inheritance works. It’s still at the core of the language design.

## Prototypal Inheritance

```
function Animal(name) {
  this.name = name;
}
Animal.prototype.walk = function() {}

function Bird(name) {
  // I can do all the things animals can do!
  Animal.call(this, name);
}
// Unlike other animals, birds can fly
Bird.prototype.fly = function() {}

// Make a new bird ..
let parrot = new Bird('parrot');
parrot.fly();
parrot.walk();
```

## ES6 Classes

The same thing with classes (much cleaner!)

* function() becomes class {}
* call() becomes extends
* Classes are standalone, self-contained object (instance) factories
  * Ultimately, they result in a prototype
  * But for the developer, they are many orders of magnitude easier to comprehend and work with

```
class Animal {
  constructor(name) {
    this.name  = name;
  }

  walk() {}
}

// Thanks to 'extends', all birds can now do all things animals can
class Bird extends Animal {
  // Birds can walk, becuase they're animals also do their own thing.
  fly() {}
}

// Make one (the same was as before, but wasn't the class creation much easier?)
let parrot = new Bird('parrot');
parrot.fly();
parrot.walk();
```

## Additional Resources

Video: [what the heck is the event loop anyway](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
[MDN inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
[MDN this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
[MDN class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)