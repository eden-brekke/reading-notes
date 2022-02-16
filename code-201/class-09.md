# Class 09 Reading Notes

## HTML and CSS Chapter 7 (pg 144-175)
Forms
### Key Topics
- How to collect info from visitors
- different kinds of form controls
- new HTML5 form controls

#### How forms work
1. A user fills in a form then presses a buton to submit the info to the server
2. the name of each form control is sent to server along with value the user inputs
3. the server processes the info using a programming language 
4. sever creats new page to send back to browser

form may have several form  controls, each gathering diff info.
        
        Name/value pair:
        username = Ivy 
      
 Some html tags related to forms:
 
      <form>
      <input>
          type="password"
          type="radio"
          type="checkbox"
          type="date"
          type="email"
          type="url"
          type="search"
      <textarea>
      <select>
      <option>
      <button>
      <label>
      <fieldset>
      <legend>
      
### Chapter 7 Summary
- Whenever you want to collect info from a visitor you will need a form which live inside the form element
- info from a form is sent in name/value pairs
- each form control is given a name and the text the user types in or the values of the options they select are sent to the server
- HTML5 introduces new form elements which make it easier for visitors to fill in forms

## Chapter 14 (pg 330-357)
Lists Tables and Forms

### Key Topics 
- Specifying bullet point styles 
- adding borders and backgrounds to tables
- changing the appearance of form elements 

#### Headers within Chapter:
- Bullet point styles 
- images for bulelts
- positioning the marker
- list shorthand
- table properties
- border on empty cells
- gaps between cells
- styling forms
- styling text inputs
- styling submit buttons
- styling fieldsets and legends
- aligning form controls:problem/solution
- cursor styles


### Chapter 14 Summary
- In addition to the CSS properties covered in other chapts which work with the contents of all elements, there are others that are used spec. for lists tables and forms
- list markers can be given different appearances using list-style-type and list-style img properties
- table cells can have diff borders and spacing in diff browsers, but there are properties you can use to control them and make them more consistent
- forms are easier to use if the form controls are vertically aligned using CSS
- form benefit from styles that make them feel more interactive


## JS and jQuery Chapter 6 (pg 243-292)
Events

#### How Events Trigger Javascript Code
When a user interacts with HTML page there are three steps involed
1. (Select element)Select the element nodes you want the script to respond to
2. (Specify Event)indicate which event on the selected nodes will trigger the response
3. (Call Code)state the code you want to run when even occurs

#### Event flow
HTML elements nest inside other elements. <br>
if you hover or click on the link, you will also be hovering/clicking on parent element 

#### why flow matters
The flow of events only really matters when your code has event handlers on an element and one of its anxestors or descendant elements

#### Where events occur
The event object can tell you where the cursor was positioned when an event was triggered
1. screen
2. page
3. client

### Chapter 6 Summary 
- Events are the browsers way of indicating when something has happened 
        - such as when a page has finished loading or a button has been clicked 
- Binding is the process of stating which event you are waiting to happen and which element you are waiting for that event to happen upon
- when an event occurs on an element it can trigger a JS function. when this function then changes the page in some way, it feels interactive
- you can use event delegation to monitor for events that happen on all of the children of an event
- the most commonly used events are W3C DOM events, although there are others.   
