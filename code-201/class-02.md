# Class 02 Reading
From the Duckett HTML book:

Chapter 2: “Text” (pp.40-61)
Chapter 10: Ch.10 “Introducing CSS” (pp.226-245)
From the Duckett JS book:

Chapter 2: “Basic JavaScript Instructions” (pp.53-84)
Chapter 4: “Decisions and Loops” only up to the section on switch statements (pp.145-162)

## HTML and CSS Chatper 2 "Text" (page 40-61)
  Text!
### Key Topics
  * Headings and Paragraphs
  * Bold Italic and emphasis
  * Structural and Semantic Mark up
  
  Structural Markup: the elements that you can use to describe both headsing and papragraphs <br>
  Semantic Markup: This provides extra info. Such as bold-italics and emphasis placed somewhere in text. <br>
  
  Headings < h1 - h6 >range from 1-6 with 1 being the biggest and 6 being the smallest <br>
  Paragraphs < p >are the main body of text within a website <br>
  Bold is < b > to make text between the tags bold <br> 
  Italics is < i > to make text between tags italic <br>
  Superscript and Subscript are < sup > amd < sub > respectively. Examples of this are exponents in math equations and references in papers. <br>
  
  To make code easier to read many times authors will use white space within the code. but the white space disappears when on the webpage. <br>
  to break a line you use the command < br /> <br>
  and to create a break between themes you would use < hr />  this will make a line <br>
      these are called empty elements and are written differently <br> 
      
  Many editors have two views: visual editor and code view  <br>
  < em > which tells which words should be emphasized default is italic <br> 
  < blockquote > to show that a block of text is a quotation <br> 
  < strong > which indicates it's important, default browser settings will make this bold <br>
  < q > element indicates a shorter quote but doesnt work in explorer so people tend to not use this element <br>
  < abbr > is used for abbreviation or an acronym. example: < p > < abbr title = "Professor" >"Prof" < / abbr > <br>
  < acronym title = "National Aeronautics and Space Administration" >"NASA" and < /acronym >  <br>
  < cite > when referencing a work  <br>
  < dfn > when you explain some terminology  <br>
  < address > has a quite specific use: to contain contact detals for author of the page <br>
  < ins > = to show content that has been inserted into a document (underline) <br>
  < del > = to show text that has been deleted (stikethrough) <br>
  < s > = to show something is no longer accurate or relevent (strikethrough) <br>
  
### Summary of Chapter 2
  * HTML elements are used to describe the structure of the page (headings, subjeadings, paragraphs)
  * They also provide semantic info (Where emphasis should be placexd, definition of acronyms, when given text is a quote)
  
  
## HTML and CSS Chapter 10 "Introducing CSS" (page 226-245)
  Introducing CSS
### Key Topics
  * What CSS does
  * How CSS works
  * Rules, properties and Values
  
Block and Inline Elements: <br>
  Block look like they start on a new line (headings, paragraphs, div elements) <br>
  Inline flow within the text and dont start on a new line (b, i, img, em, span) <br>

CSS lets you create rules to ontrol the way each element appears <br>
Example Styles  <br>
Boxes = width and height, borders (color width and style), background color and images, and position in the browser window <br>
text = typeface, size, color, italics, bold, uppercase, lowercase, small-caps  <br>
Specifics: lists, tables and forms  <br>

Example code:  <br>
    p {
        font-family: Arial;}
    h1, h2, h3 {
                font-family: Arial;
                color: yellow; }
  Where color/font-family are porperties and Arial/yellow are values <br>
  Properties = aspects you want to change <br>
  value = specific setting  <br>
  
  External CSS:  <br>
  < link > element will allow you to link a CSS file  <br>
  href = the specific path <br>
  type = type of document to link <br>
  rel = the relationship between HTML and the file linked <br>
  < link href="css/style.css" type="css" rel="stylesheet" /> <br>
  
  Interal CSS:  <br>
  < style > used to specify CSS  <br>
  Example:  <br>
      < style type="text/css >
        Insert CSS code here  <br>
       < /style > closing tag
       
|Selector|Meaning|Example|
|:---:|:---:|:---:|
|Universal|Applies to all elements in document|\*{}|
|Type|Matches element names|h1{}|
|Class|Matches an elemet whose class attribute has values tht match to one specified after the period symbol|.note{}|
|ID|matches element whos ID matches the one specified|#id{}|
|Child|Element that is direct child of another|li>a{}|
|Descedant|element that is descendent of another specified element|p a {}|
|Adjacent sibling|element that is the next sibling of another|h1+p{}|
|General Sibling|element that is a sibling of another although does not have to be directly preciding|h1~p{}|

 <br>
 
 CSS rules cascade <br>
 Last rule = if two selectors are identical the latter of the two will win <br>
 Specificity = the more specific will win <br>
 Important = You can add !important to override any other rules applied to this element <br>
 
 Inheritance: you can specify inherit so that child elements will follow the parent element 
 

### Summary of Chapter 10
  * CSS treats each HTML element as if it appears inside its own box and uses rules to indicate how that element should look
  * rules are made up of selectors (that specify the elements the rule applies to) and declarations (that indicate what these elements should look like)
  * differenty types of selectors allow you to target your rules at different elements
  * Declarations are made up of two parts: the properties of the element that you want to change,  
<br> and the values of those properties. or example, 
<br> the font-family property sets the choice of font, 
<br> and the alue arial specifies areial as the preferred typeface
  * CSS rules usually appear in a separate document, although they may appear within an HTML page


## JavaScript and jQuery Chapter 2 "Basic Javascript Introduction" (page 53-84)
  Basic JS 
### Key Topics
  * The language: Syntax and Grammar
  * Giving instructions: for a browser to follow
  
  Statements = each step of instructions for the computer to follow <br>
    Example: var today = new Date(); is a statement  <br>
   remember: javascript is case sensitive  <br>
   Statements can be organized into code blocks <br>
   Statements each start a new line of code <br>
   {} anything within the brackets are the code blocks <br>
   
 Comments = you should write comments that explain what your code does. Help to make the code easier to read and understand  <br>
 You can write multiple line comments with / * and * \ to open and close or single line comments with / /  <br>
 
 Variables = a box to store a bit of data <br>
    example var quantity; makes a variable named quantity  <br>
             quantity = 3; makes it so quantity now holds the value 3 <br>
             
             
  Data types:
   * Numerica Data numbers  <br>
   * String Data Text "in quote"  <br>
   * Boolean Data (true/false)  <br>

Rules for Variable Naming:
1. Name must begin with a letter $ or _ but no numbers
2. must contain letters, numbers, $ or _ but cannot use - or . 
3. cannot use keywords or reserved words
4. variables are case sensitive 
5. use a name thats descriptive 
6. camal case your variables, start with lowercase and eachword after cap the first letter: firstName

Array = special type of variable. doesnt store one value but a list of values <br>
  array literal example : var colors;  <br>
             colors = \['white', 'black', 'custom'] <br>
  array constructor example : var colors = new Array('white', 'black', 'custom'); <br>
  
  you can access or change the values within an array by calling them "colors\[2]" would return custom while colors\[0] would return white <br>
  
Expressions : evalutes into (results in) a single value.  <br>
    Two type expressions <br>
    1. Assign a value to a variable <br>
        var \color = 'beige'; <br>
    2. use two or more values to return a single value <br>
        var \area = 3 * 2;  <br>
          which result in 6 <br>
          
Opertors: 
  assignment operators = 
  arithmetic operators  * (Multiply)  <br>
                        + (plus)  <br>
                        = (equals)  <br>
                        / (divide)  <br>
                        ++ (add 1) <br>
                        -- (minus 1)  <br>
                        % (divide two values return remainder)  <br>
  string operators 'Hi' + 'there' <br>
  
### Summary of Chapter 2
  * A script is made up of a series of statements. Each statement is like a step in a recipe
  * Scripts contain very precise instructions. For example you might specify that a value must be remembered before creating a calculation using that value
  * Variables are used to temporarily storepieces of information used in the script
  * Array are special types of variables that store more than one piece of related info
  * JS distinguishes between numbers (0-9) string (texts) and boolean (true or false)
  * expressions evalute into a single value
  * expressions rely on operators to calculate a value



## JavaScript and jQuery Chapter 4 "Decisions and Loops" --up to Switch statements-- (page 145-162)
  Decisions and Loops
### Key Topics
 * Evaluations 
 * Decisions
 * Loops

Evaluations: 
To plan for writing code for evaluations it helps to draw out a flowchart  <br>
in terms of code Conditions are conditional statements are used <br>
  two components to a decision
  1. Expression is evaluated and returns a value
  3. Conditional statement says what to do in a given situation 

Example code: if \(score > 50) {
                document.write('You passed');
                } else {
                document.write('Try again');
                }
 
* == is equal to 
* != is not equal to 
* === strict equal 
* !== strict not equal 
* \> greater than 
* < less than 
* >= greater than  or equal to  
* <= less than or equal to  
* && logical and
* || logical or
* ! logical not

If statement evaluates a condition and returns a boolean  <br>
If else statements evaluate a condition, returns a boolean then runs else if boolean for if is false

### Summary of Chapter 4
  * Conditional statements allow your code to make decisions about what to do next 
  * comparison operators (===. !==. ==. !=. <, >, <=, >=)are used to compare two operands
  * Logical operators allow you to combine more than one set of comparison operators
  * if...else statements allow you to run one set of code if a condition is true and nother if it is false.

