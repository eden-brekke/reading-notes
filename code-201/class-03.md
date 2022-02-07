# Class 03 Reading Notes

## HTML and CSS Chapter 3 
Lists <br>

### Keytopics
 * numbered lists
 * bullet lists
 * definition lists
 
Ordered Lists: lists where items in the list are numbers  <br>
Unordered lists: lists that begin with bullets <br>
Definition lists: made up of a set of terms along with the definitions for those terms <br>

< ol > for ordered lists <br>
< ul > for unordered lists  <br>
< li > for the list items.  <br>
< dl > for definition lists  <br>
  < dt > for the defined term  <br>
  < dd > for the definition for the term  <br>
 
 You can make nested lists  <br>
  < ul > <br>
      < li > <br>
      < li > <br>
        < ul >  <br>
          < li > <br>
          < li > <br>
         < / ul > <br>
       < li > <br>
   < / ul >     <br>

### Chapter 3 Summary 
 * There are three types of HTML lists: ordered, unordered and definition
 * Ordered list use numbers
 * Unordered list use bullets
 * definition lists are used to define terminology 


## HTML and CSS Chapter 13
Boxes <br>

### Key Topics
* Controlling Size of boxes
* Box model for borderes, margin and padding
* Displaying and Hiding Boxes 

#### Box Dimensions  <br>
  By default boxes are just big enough to hold their contents <br>
  width: controls width of box <br>
  height: controls height of box  <br>
  min-width: sets a minimum width for box  <br>
  max-width: sets a maximum width for box  <br>
  min-height: sets a min height for box  <br>
  max-height: sets a max height for box  <br>
  overflow: tells browers what to do if content of box is larger than box itself <br>
      overflow: hidden; hides any extra content <br> 
      overflow: scroll; adds a scrollbar to box if needed <br>
      
 <br>
 
 Border: every box has a border, separates edges of one box to another <br>
 Margin: sits outside edge of border, settings width creates a gap between two borders of adjacent boxes  <br>
 Padding: space between border of box and any content contained within <br>
 
 <br>
#### Border
 
 border-width: control border width, a few ways to do this:  <br>
  border-top-width: <br>
  border-right-width: <br>
  border-bottom-width: <br>
  border-left-width: <br>
  
   <br>
   
 Border-style: a few ways to change style:  <br>
 solid - single solid line <br>
 dotted - series of dots <br>
 dashed - series of short lines <br>
 double - two solid lines <br>
 groove - appear carved into page  <br>
 ridge - appear to stick out from page  <br>
 inset - embedded into page  <br>
 outset - coming out of screen  <br>
 hidden/none - no border shown <br>
 additionally you can change the top/bottom/right/left border style individually just as you did with the width  <br>
 
  <br>

 Border-color, similar to the above traits can be done to top/bottom/right/left <br>
 
 <br>
 
 You can right all the border styling on the same line <br>
 example: border: 3px dotted red; will change the border width/style/color  <br>
  
  <br>
  
#### Padding
 Allows you to specify how much space should appear bertween the content of an element and its border <br>
 padding-top/right/bottom/left <br>
  <br>
  
#### Margin 
 Margin controls the gap between the boxes. value commonly given in pixels.  <br>
 margin-top/right/bottom/left <br>
  <br>
  
#### Centering content
 Want to center a box?  <br>
 You can set a boxes left-margin and right-margin to auto <br>
  You can also center text within a box with text-align <br>
  Text-align works with center/right/left  <br>
  
   <br>
#### Change inline/block
 With Display!  <br>
 display: inline - act like an inline element <br>
 display: block - act like a block element <br>
 display: inline-block allows block level element to flow like an inline element while retaining other block-level elements <br>
 display: none - hides an element from the page <br>
      You can also change visibility of element with command "visibility: hidden or visible;" <br>
      
#### CSS3 Border image
  border-image applies image to border of box <br>
  Requires three pieces of info:  <br>
  1. URL of img
  2. where to slice img 
  3. what to do with straight edges
      * possible values are: stretch, repeat, and round
  <br>

#### CSS3 Box Shadows 
  box-shadow allows you to add a drop shadow around a box (works similarly to text-shadow property) <br>
  Horizontal offset: negative values of position to the left of box <br>
  vertical offset: negative value to top of box  <br>
  blur distance: if omitted the shadow is solid like a border  <br>
  spread of shadow: positive value cause shadow to expand in all direction, negative will contract  <br>
 <br>
 
#### CSS3 Rounded corners and Elliptical shapes
  border-radius: create rounded corners on any box  <br>
  border-top-right-radius <br>
  border-bottom-right-radius <br>
  border-bottom-left-radius <br>
  border-top-left-radius <br>
  Shorthand: in clockwise order of top/right/bottom/left <br>
  border-radius: 5px, 10px, 5px, 10px;  <br>
  <br> 
  border-top-left-radius: 80px 50px; will return an elliptical shape 
  

### Chapter 13 Summary 
  * CSS treats eqach HTML element as if it has its own box
  * you can use CSS to control the dimensions of a box
  * You can also control the borders, margins and padding for each box with CSS
  * it is possible to hide elements using the display and visibility properties 
  * block-level boxes can be made into inline boxes and inline boxes made into block level boxes
  * legibility can be improved by controlling the width of boxes containing text and the leading
  * CSS3 has introduced the ability to create image borders and rounded corners. 

## JS and jQuery Chapter 4
Switch Statements <br>

A switch statement starts with a variable called the switch value.  <br>
Each case indicates a possihble value for this variable and the code that should run if the variable matches the value <br>
You'll have a default option that is run if none of the cases match <br>
If a match is found, then that code is run; then the break statement stops the rest of the switch statements.  <br>

#### Type coercion and Weak Typing
If you use a data type JS doesnt understand it tries its best to understand it instead of erroring.  <br>
    Type coercion : converting data type behind the scenes to complete an operation <br>
    Weak Typing: data type value can change  <br>
    
#### Truthy and Falsy Values 
Falsy values are treated as if they are false <br>
Truthy values are treated as if they are true  <br>

#### Loops 
For: if you need to run a code for a specific number of times, the for loop is useful  <br>
      In a for loop the condition is usually a counter which is used to tell how many times the loop should run <br>
While: if you don't know how manyu times the code will need to run, a while loop is useful.  <br>
        In a while loop the condition is something other than a counter and teh code will continue to loop for as long as the condition is true  <br>
Do while: the do...while loop is similar to the while loop, with one key difference.  <br>
          it will always run the code in the curly braces at least once, even if the condition evaluates false <br>
          
Initialization: Create a variable and set it to 0 (variable is commonly called i, and acts as a counter) (let i = 10)  <br>
Condition: loop should continue to run until counter reaches a specified number (i < 10)  <br>
Update: every time a loop has run the statement in curly braces it adds one to the counter (i++)  <br>

#### key loop concepts
break: breaks out of the loop
continue: tells interpreter to stop current iteration and update and check condition again 

### Summary for Chapter 4 Switch Satements and Loop
  * Switch statements allow you to compare a value against possiblke outcomes (and also provides a default option if none match)
  * Data types can be coerced from one type to another
  * All values evaluate to either truthy or falsy
  * There are three types of loops: for, while, and do...while. Each repeats a set of statements
