# Class 08 Reading Notes

## Article [Learn CSS-Layout](https://web.dev/learn/css/layout/)
An overview of layout methods <br>

CSS layouts overtime: <br>
1996: CSS 1 Floats  <br>
1998: CSS 2 <br>
2010: CSS 3  <br>
2012: Media Queries, Flexbox  <br>
2017: grid <br>
2019: intrinsic web design  <br>
2021: Container Queries  <br>

#### Understanding the display property
Display does two things: 
1. determine if the box its in acts inline or block
2. determines how an elements children should behave

#### Flexbox and Grid:
These are the two main layout mechanisms 
- Flexbox is for one-dimensional layouts
- Grid is designed to control multi-axis layouts 

#### Flow Layout
If not using grid or flexbox then the elements are in normal flow <br>
number of layouts used in normal flow:
- inline block
- floats
- multicolumn layout
- positioning

#### Wrap up
There are a lot of choices and flexibility with CSS layout, use them together to create a dynamic webpage.



## HTML and CSS Chapter 15 (pg 359-403)

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
