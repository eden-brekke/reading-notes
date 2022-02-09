# Class 4 Readings

## HTML and CSS Chapter 4 pg 74-93

Links
### Key topics

  * Creating Links between pages
  * Linking to other sites
  * Email Links 

#### Links

Links are created using the < a> element. <br>
Users can click on anything between the opening a tag and the closing a tag  <br>
You specify which page is linked by using the href attribute

#### Relative URLs

|Relative Link Type|Example|
|:---:|:---:|
|Same Folder|< a href="stuff.html"> Thing to Click on < /a >|
|Child Folder|< a href="child/stuff.html"> Thing to Click on < /a >|
|Grandchild Folder|< a href="child/grandchild/stuff.html"> Thing to Click on < /a >|
|Parent Folder|< a href="../stuff.html"> Thing to Click on < /a >|
|Grandparent Folder|< a href"../../stuff.html"> Thing to Click on < /a >|

#### Other Link Types

email links : will use < a href="mailto: email@email.domain"> email me! < /a > <br>
target : used to have a link open in a new window " target = _ blank " <br>
linking within a single page: you'll assign an id to the element and then link to the specific id with a href=#id <br>

### Summary of Ch4 
  * Links are created using the < a > element
  * the < a > element uses the href attribute to indicate the page you are linking to 
  * if you are linking to a page within your own site, it is best to use relative links rather than qualified URLs
  * You can create links to open email programs with an email address in the 'to' field
  * You can use the id attribute to target elements within a page that can be linked to
 

## HTML and CSS Chapter 15 pg 358-404

Layouts <br>

### Key Topics

  * Controlling the Position of Elements
  * Creating Site Layouts
  * Designing for Different sized Screens

#### Key Concepts for Positioning Elements

Building Blocks: CSS treats HTML element as if its in its own box <br>
                  This box will either be block level or inline <br>
Containing Elements: if One block level element sits inside another block level element then the outer box is known as the containing or parent block <br>

#### Controlling the Position of Elements 

Normal flow: every block level element appears on a new line (default behavior) <br>
            position:static <br> <br>
Relative Positioning: moves element from its default position and shifts it to the top/right/bottom/left. <br>
            position:relative <br> <br>
Absolute Positioning: Positions an element in relation to its containing element. they move as the user scrolls up/down the page <br>
            position:absolute <br> <br>
Fixed Positioning: a form of absolute, fixed to a position and does not affect position of surrounding elements, nor does it move when user scrolls <br>
            position:fixed <br> <br>
Overerlapping elements: use z-index <br> <br>
Floating Elements: takes element out of normal flow and position far left or right of containing box <br>
            float:right float:left <br>
You can clear floats <br>
Clear: right: right hand side of box wont touch elements <br>
clear: left: left hand side of box wont touch elements <br>
Clear: both: both side wont touch elements <br>
clear: none: elements can touch either side of box <br>

#### Formatting layouts

When it comes to multidevice layout formatting you need to consider how your site will look on each. <br>
You can use fixed and liquid width layouts, there are advantages and disadvantages to both <br>

Fixed:  <br>
  * Advantage: pixel values are accurate. designer control, size of images will remain the same
  * Disadvantage: can leave big gaps on your site. users screen is higher than designers, so text can look too small. if user increases text size, it will move out of alloted space. site will work best on screens similar to designers. page will take up more vertical space than a liquid layout

<br>

Liquid: <br>
  * Advantage: pages expand to fill window, will also contract, design is tolerant of user settings. 
  * Disadvantage: Design can look different than you intend, if user window is long, can make text very long, hard to read, same idea with short window, hard to read. 

#### CSS Frameworks
  
  Aim to make your life easier, providing code for common tasks such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on.  <br>
    * Advantage: save you from repeating code, tested across different browser <br>
    * Disadvantage: often require you to use class names in HTML that only control presentation of th epage rather than describes its content.  <br>

### Summary of Ch 15 
  
  * < div > elements are often used as containing elements to group together sections of a page
  * browsers display pages in normal flow unless you specify relative, absolute, or fixed positioning
  * the float property moves content to the left or right of the page and can be used to create multi-column layouts (floated items require a defined width)
  * pages can be fixed width or liquid layout
  * designers keep pages within 960-1000 pixels wide and indicate what the site is about within the top 600 pixels (to demonstrate its relevance without scrolling)
  * grids help create professional and flexible designs
  * CSS frameworks provide rules for common tasks
  * you can include multiple CSS files in one page 


## JS Chapter 3 pg 86-99

#### Declaring and calling a Function

Functions: let you group a series of statements together to perform a specific task. <br>
If a different part of a script repeat the same task, you can reuse the function  <br>

Declare:  <br>
keyword name(){codeblock} <br>
Example: <br>
function sayHello(){ <br>
document.write('Hello'); <br>
}  <br>

Call:  <br>
sayHello();  <br>

Sometimes a function needs information so you can add within the paranthese' the parameters needed
example:  <br>
function getArea(width, height){ <br>
return width * height; <br>
}  <br>

There are a few ways to feed in those parameters  <br>
you can call the function: getArea(3, 5); with the parameters  <br>
Or you can assign the parameters: width = 3; and height = 5;  <br>

Getting a single value Example code:  <br>
function calculateArea(width, height){ <br>
let area = width * height;  <br>
return area; <br>
} <br>
let wallOne = calculateArea(3, 5);  <br>
let wallTwo = calculateArea(8, 5); <br>

Getting multiple values out of a function Example code:  <br>
function getSize(widthm height, depth){  <br>
let area = width * height; <br>
let volume = width * height * depth;  <br>
let sizes = SquareBracket area, volume CloseSquareBracket;  <br>
return sizes; <br>
}  <br>
 <br>
let areaOne = getSize(3,2,3)(0); <br>
let volumeOne = getSize(3,2,3)(1); <br>
Where above second set of paraenthese are actually square brackets (md limit) <br>

Methods, and Objects <br>
will be touched on later  <br>

### Summary for Ch 3

  * Functions allow you to group a set of related statements together that represent a single task
  * Functions can take parameters (information required to do their job) and may return a value


## Article [6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)

### How does pair programming work? 

 Commonly involves two roles: the driver and the navigator <br>
 Driver is the programmer who is typing <br>
 Navigator is the one who is using their words to guide the driver, but doesn't provide direct input.  <br>
 

### Why Pair program?

While learning to code, developers likely study several programming languages. There are fundamental skills that help anyone learn a new language.  <br>
  * Listening: hearing and interpreting the vocabulary 
  * Speaking: using the correct words to communicate an idea
  * Reading: Understanding what written language intends to convey. 
  * Writing: producing from scratch a meaningful, well structured solution
 
 Skills to foster <br> 
 1. Greater Efficiency <br>
      pair programming takes longer but doesn't require later effort in troubleshooting/debugging <br>
 2. Engaged Collaboration <br>
      experience is more engaging with a partner <br>
 3. Learning from Fellow Students <br>
      everyone has a different approach to problem solving, working with others gives you a new perspective <br>
 4. Social Skills <br>
      pair programming improves your social skills! <br>
 5. Job Interview Readiness <br>
      ability to work with others is a huge plus when it comes to job searching <br>
 6. Work Environment Readiness <br>
      You hit the ground running when you graduate from code fellows! <br>

