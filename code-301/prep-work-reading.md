# Readings: Introduction to React and Components
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[Component-Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)

1. What is a “component”? 
  A component is a modular, portable, replaceable and reusable set of functionality that encapsulates its function and exporting it as a higher-level interface. It's a software object which is suppose to interact with other components encapsulating functionality or a set of functionalities. It has a defined interface and conforms to behavior common to all components within an architecture. Software component can be thought of as a unit of composition with a specified interface and context dependencies. It can be deployed independently and is subject to the composition by third parties. 
2. What are the characteristics of a component?
  * Reusability - designed to be reused in different situations in different applications. 
  * Replaceable - may be freely substituted with other similar components 
  * Not-Context-Specific - Designed to operate in different environments and contexts
  * Extensible - Can be extended from existing components to provide new behavior
  * Encapsulated - Depicts the interfaces, allow the caller to use its functionality but doesn't expose details of the internal variables or state
  * Independent - Designed to have minimal dependencies on other components 
3. What are the advantages of using component-based architecture? 
  * Ease of deployment - As new compatible versions become available, easier to replace existing versions with no impact on other components or the system
  * Reduce Cost - the use of third party components allows you to spread the cost of development and maintenance 
  * Ease of development - Components implement well-known interfaces to provide defined functionality, allowing development without impact on other parts or system
  * Reusable - Can be used to spread development and maint cost across several applications or systems
  * Modification of Technical Complexity - Component modifies the complexity through the use of a component container and its services 
  * Reliability - Overall system reliability increases since each reliability of each individual component enhances reliability of the whole system via reuse. 
  * System Maintenance and Evolution - Easy to change and update the implementation without affecting the rest of the system 
  * Independent - independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development. 

[What is Props and How to Use it in React](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0)

1. What is “props” short for?
  Short for properties which are returned as an object
2. How are props used in React?
  Used for passing data from one component to another
3. What is the flow of props?
  Data with props are being passed in a uni-directional flow (one way from parent to child) and is read-only, cannot be changed by child.

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
I'm a little uncertain about how to get a react.. file set up, do I need to use a JSX file? Can I just use a JS file? Do I need an html file attached to it, it's specified that DOM manipulation is different than react DOM stuff, but I'm not sure why. I'm also feeling really unclear on what benefit there is to using react to do these simple tasks that are being shown in the examples. Is it just to get us used to using react so that it can be used for more complex functions down the line? can you mix everything we've learned together or 

```
New Reading
```

# Readings and Resources: ES6 Classes

Below you will find some reading material, code samples, and some additional resources that will help you to better understand ES6 Classes

Watch the [Shred Talk: ES6 Classes](https://www.youtube.com/watch?v=9Yc5J3Ap9-4)
Review the [Demo Code](https://codefellows.github.io/code-301-guide/curriculum/prework/classes/DEMO.html)

### Free hand notes from the video 

Dive into data modeling, specifically through using javascript constructor functions and prototypes. 
and more specifically they will get into ES6 classes which should make data modeling much more obtainable and easier to understand 
before we jump into code its important to understand the process and functions of data modeling
think about the data model: modeling some real world object
for example: a person 
most objects have a couple of things that are unique about them
attributes: nouns, things about you, so for a person, hair color, height, weight, location etc. things you can describe
they also have behaviors: we describe behaviors in code as methods, things you can do, or verbs! things such as the ability to walk 

we can model these out using straight objects, using json directly and also with constructors
but what we havent done much of is subclassing
and by subclassing, so using person as example, maybe theres a certain kind of person. so everyones a person but an adult has different features than a child 
so in that case you can make a child with special characteristics but is still a person object. this is called inheritance 
you'll see this with vehciles and stuff (planes, motorcycles etc,) they share some of the same attributes but they can vary widely in some of their behaviors or maybe the presence of absence of some of the attributes


person 
  attributes: hair color, height, weight, location
  behaviors: (verbs) - walk(), speak(), drive() 

build out an animal class using a constructor

```js 
const Animal = function(name, legs){
  this.name = name;
  this.legs = legs;
  this.eat = function(){
    this.isEating = true;
  }
}

Animal.prototype.walk = function(){
  this.isWalking = true;
}

const Dog = function(name, legs){
  Animal.call(this, name, legs);
}
Dog.prototype = Object.create(Animal.prototype);

let puppy = new Dog('blake', 4);
puppy.walk();
puppy.eat();
console.log(puppy);
console.log(puppy instanceof Animal);
console.log(puppy instanceof Dog);
```

Now rewrite using classes

```js
class Animal {
  constructor(name, legs){
    this.name = name;
    this.legs = legs;
  }
  walk(){
    this.isWalking = true;
  }
  
  eat(){
    this.isEating = true;
  } 
}

class Dog extends Animal {
  
  constructor(name, legs, furType){
    super(name, legs); // run the parent method to create a new instance
    this.furType = furType; // new attribute that only dogs have
  }
  speak(){
    console.log('woof!');
  }

}
let rosie = new Dog ('rosie', 4, 'Short Hair');
rosie.walk();
rosie.eat();
console.log(rosie);
rosie.speak();
```

prototypes are much more memory efficient, especially for subclasses. 


Complete the [Assignment](https://codefellows.github.io/code-301-guide/curriculum/prework/classes/LAB.html)

## Objects and Inheritance

JavaScript objects use prototype-based inheritance. Its design is logically similar (but different in implementation) from class inheritance in strictly Object Oriented Programming languages like Java and C#. <br>

It can be loosely described by saying that when methods or properties are attached to object’s prototype they become available for use on that object and its descendants, but not directly attached to them.<br>

When you use class and extends keywords internally JavaScript will still use prototype-based inheritance. It just simplifies the syntax (this is often called “Syntactic Sugar”). While classes are easier to use, it’s still very important to understand how prototype-based inheritance works. It’s still at the core of the language design.

## Prototypal Inheritance

```js
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