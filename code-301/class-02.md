# Readings: State and Props
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[React lifecycle](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)
* Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?
  Based off the diagram it looks like the render happens first, followed by React updating DOM and refs, then componentDidMount happens. 
* What is the very first thing to happen in the lifecycle of React?
  The first thing to happen is that the constructor is mounted. this is when an instance of a component is being created and inserted into the DOM. 
* Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React 
Updates
  1. Constructor
  2. Render
  3. ComponentDidMount
  4. React Updates 
  5. ComponentWillUnmount
* What does componentDidMount do?
  This is a method, and it's invoked immediately after a component is mounted. It's used to load anything that uses a network request or initializes the DOM.

## Additional Resources
[React Bootstrap Documentation](https://react-bootstrap.github.io/)
[Netlify](https://www.netlify.com/)

## Videos
[React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)

* What types of things can you pass in the props?
  Think of these like arguments for a function. When you create a component in a react, and you want to render it, you pass it the props you want to give to it. What you initialize your component to, or what you want your component to render like. Can also store things like titles and subtitles. 
* What is the big difference between props and state?
  Props you pass into a component, and are handled outside of the component and must be updated outside of the component, whereas states are handled inside of the component, and you can update it within the component. 
* When do we re-render our application?
  When you change the state within the application it will re-render that section of the application
* What are some examples of things that we could store in state?
  state will store things that we need to keep updating, it's there for things that we need to rerender based on what the user has done. 


## Bookmark/Skim
[React Docs - State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
[React Docs - handling events](https://reactjs.org/docs/handling-events.html)
[React Tutorial through ‘Developer Tools’](https://reactjs.org/tutorial/tutorial.html)

## Assignment Instructions
Read for understanding the assigned resources for this class and watch any assigned videos. Also skim and bookmark the additional resources provided. Prepare an entry for your Readings Notes Repository that answers each and every question presented above.

Make a section in your notes titled ## Things I want to know more about, and anytime a question arises in your mind, or something catches your curiosity, write it down under this heading.

## Things I want to know more about