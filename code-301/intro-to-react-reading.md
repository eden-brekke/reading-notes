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


