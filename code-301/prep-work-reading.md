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
  // Birds can walk, because they're animals also do their own thing.
  fly() {}
}

// Make one (the same was as before, but wasn't the class creation much easier?)
let parrot = new Bird('parrot');
parrot.fly();
parrot.walk();
```

## Additional Resources

Video: [what the heck is the event loop anyway](https://www.youtube.com/watch?v=8aGhZQkoFbQ)

#### Notes from the video 

the event loop has one simple job. <br>
look at the stack (things within the script that have been invoked to run, the stack works by adding things ontop of the stack then popping them off the top when they're done) <br>
and at the task queue (things to be done) <br>
and it takes the first thing in the queue <br>
and pushes it onto the stack. <br>
You use the built in function setTimeout(which I used for the animations!) in conjunction with the event loop, <br>
you can use this to defer a function until the stack is clear, so it will run after other things have ran. <br>
This works because the event loop HAS to wait for the stack to be clear before it can push anything else onto the stack <br>
You need to be careful about blocking the queue <br>
Too many animations can be bad if you're not careful, same with image rendering, and you want your website to be fluid. <br>

[MDN inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

#### Notes on Inheritance 

When it comes to inheritance, JS only has one construct: objects. <br>
Each object holds private property which holds a link to other objects called its prototype  <br>
Prototype object has a property of its own and so on until it hits null.  <br>
All objects in JS sit just below null on top of the prototype chain  <br>
<br>
Inheriting properties - JS objects are dynamic 'bags' of properties.  <br>
Each object can be linked to a prototype object  <br>
 <br>
Inheriting 'methods' - JS does not have 'methods' in the form that class based languages define them  <br>
in JS any function can be added to an object in the form of a property  <br>
Inherited functions act just as any other property, overriding methods  <br>
when an inherited function is executed, the value of 'this' points to the inheriting object, not the prototype object.  <br>
 <br>
object.create() calling this method creates a new object.  <br>
prototypes of this object is the first argument of the function <br>
 <br>
You can also use delete and new objects as well in conjunction with create method. 
 <br>
class keyword can be used to implement classes, and can be used with constructor, static, extends and super  <br>
constructor refers to a constructor <br>
static refers to a method that can be called without instantiating their class and cannot be called through the class instance. often used to create utility functions <br>
extend inherits a constructors attributes  <br>
super will also call to a parent construtor within a child constructor  <br>

[MDN this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

#### notes on this

A functions this keyword behaves differently in strict mode and non-strict mode <br> 
in most cases the value of this is determined by how a function is called (runtime binding)  <br>
ES5 introduced bind() method which sets the value of a functions this regardless of how its called <br> 
ES2015 introduced arrow functions which dont provide their own this binding (retains the this value of an enclosing lexical context) <br>
this can refer to a global object, when not in strict mode if it's called within a function it'll reference the global object <br>
In strict if it's used within a function but not in reference to a object it will return undefined  <br>
The behavior os this in classes and functions is similar but within a class constructor, this is a regular object. <br> 
all non-static methods within the class are added to the prototype of this  <br>
Unlike base class constructors, derived constructors have no initial this binding  <br>
calling super() creates a this binding within the constructor  <br>
Within an arrow function this retains the value of the enclosing lexical context's this. in global code it will be set to the global object  <br>
essentially this is a getter and setter  <br>

[MDN class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

#### notes on classes 

classes are special functions, so just as you can define a function expression and declaration, the class syntax has two components class expressions and class declarations.  <br>
 <br>
class declarations: to declare a class you use the class keyword with the name of the class  <br>
an important difference between function declarations and class declarations is that while functions can be called in code that appears before they are defined, classes must be defined before they can be constructed  <br>
 <br>
Class expressions: another way to define a class, can be named or unnamed  <br>
the name given to a named class expression is local to the class's body, it can be accessed via the name property  <br>
 <br>
Class body and method definitions  <br>
the body of a class is the part thats within the {}  <br>
This is where you define class members, such as the methods or constructor  <br>
 <br>
Strict mode  <br>
the body of a class is executed in strict mode, code written here is subject to stricter syntax for increased performance  <br>
 <br>
Constructor method is a special method for creating and initializing an object created with a class.  <br>
there can only be one special method with the name constructor in a class.  <br>
 <br>
Static initialization blocks  <br>
Class static initialization blocks allow for flexible initialization of class static properties, <br>
including the evaluation of statements and granting access to a private scope  <br>
multiple static blocks can be declared and they can be interleaved with declaration of static properties and methods  <br>
 <br>
Static methods and properties <br>
the static keyword defines a static method or property for a class. <br>
where static members are called without instantiating their class and cannot be called through a class instance.<br>
Static methods are used to create utility functions, <br>
static properties are useful for caches, fixed-configs, or any other data you don't need to be replicated across instances <br>
<br>
Binding this with prototype and static methods <br>
When a static or prototype method is called without a value for this, the this value will be undefined <br>
<br>
Subclassing with extends <br>
The extends keyword is used in class declarations or expressions to create a class as a child of another class <br>
if there is a constructor present in the subclass, it needs to first call super() before using 'this'<br>
<br>
Super class calls with super <br>
The super keyword is used to call corresponding methods of super class. this is one advantage over prototype-based inheritance <br>
<br>
Species <br>
You might want to return array objects in your derived array class. The species pattern lets you override default constructors <br>
<br>
Re-running a class definition <br>
A class cannot be redefined, attempting to do so will return a syntax error
<br>