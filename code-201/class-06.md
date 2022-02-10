# Class 06 Reading notes

## Article 1 [Understanding the problem domain is the hardest part of programming](https://simpleprogrammer.com/understanding-the-problem-domain-is-the-hardest-part-of-programming)

#### What is the hardest part of writing code? 
  There are some common answers to this question <br>
  - Learning a new technology
  - Naming things
  - Testing your Code
  - Debugging
  - Fixing bugs
  - Making Software Maintainable

Learning the problem domain seems to actually be the hardest <br>
When learning you need a familiar and simple domain to focus on the building blocks of coding <br>
Instead you can find yourself focusing on the wrong aspects and getting stuck in overcomplicating your work. <br>
If you can't really see what you're trying to build or create, then it's really hard to put the building blocks together <br>
<br>
Some common steps to putting together a puzzle are:
  1. Figure out the major components of the picture
  2. Sort the pieces by color or component
  3. Put together all the border pieces
  4. Put together each compoenent of the picture from the pules you created
You should do this for programming as well! Break everything into digestable steps. <br> 

If understanding the problem domain is the most difficult part of programming, what can you do to fix it? <br>
1. Make the problem domain easier
2. Get better at understanding the problem domain 



## Article 2 [What's the difference between primitive values and object references in JavaScript?](https://betterprogramming.pub/intermediate-javascript-whats-the-difference-between-primitive-values-and-object-references-e863d70677b)

### Key Topics: 
- What JavaScript Data Types Fall into each Category
- The Difference between a value and a reference 
- The difference between immutable and mutable data
- Practical examples comparing how primitive values and object reference work

#### JavaScripts Either Data Types 
1. Boolean
2. Null
3. Undefined
4. Number
5. BigInt
6. String
7. Symbol
8. Object 
    - Array, functions, and dates are subcategories of objects <br>


Primitive values can be stored in variables directly <br>
Objects are stored as references <br>
A variable that has been assigned an object doesn't store the object, but stores the memory address of the object <br>
Primitive values are immutable and can't be changed once created <br>
Object references are mutable and can be changed <br>
Since objects are stored as references, special care must be taken when duplicating objects and when performing equality checks on objects <br>
Understanding how these operations work can be confusing for newcomers to JavaScript <br>


## JS and jQuery Chapter 3 pg 100-105

#### What is an object?

Objects group together a set of variables and functions to create a model of something you would recognize from the real world. <br>
In an object, variables and functions take on new names. <br>
Variables become known as properties  <br>
Functions become known as methods  <br>

#### Programmers use a lot of name/value pairs: 
- HTML: attribute names and values
- CSS: property names and values
- In JavaScript
  - Variables have a name: can assign string, number or boolean
  - Arrays have a name and group value
  - Named Functions have a name and a value, value is a set of statements
  - Objects consist of a set of name.value pairs

#### Creating an object with Literal Notation
Example in book: 
                    
            let hotel ={
            name: 'Eden',
            rooms: 40,
            booked 25,
            checkAvailability: function (){
              return this.room - this.booked;
              }
            };
          
#### Accessing an Object and dot notation:
you can access the properties or methods of an object using dot notation <br>
You can also access properties using square brackets  <br>

Example code in book:
            
            let hotelName = hotel.name;
            let roomsFree = hotel.checkAvailability();
  
 Where hotel is the object and after the . are the property/method names

## JS and jQuery Chapter 5 pg 183-242
Document Object Model

#### Caching Dom Queries
Methods that find elements in the DOM tree are called DOM queries.  <br>
When you need to work with an element more than once, you should use a variable to store the result of this query  <br>

        getElementById('one');
        
 When people talk about storing elements in vairables, they are really storing the location of the elements within the DOM tree in a variable <br>
 The properties and methods of that element node work on the variable.  <br>
       
        let itemOne = getElementById('one');
        
#### Methods that select individual elements
getElementById() and querySelector() can both search an entire document and return individual elements  <br>
Both use similar syntax.  <br>

getElementById() is quickest  <br>
querySelector() is more recent add to DOM <br>
  
        document.getElementById('one')

Where document is the object, and  <br>
getElementById() is the method and <br>
('one') is the parameter
 
#### Selecting An Element From a Nodelist

There are two ways to select an element from a NodeList:  <br>
The item() method and array syntax  <br>
Both Require the index number of the element you want  <br>

Example Code: 
               
     The item() method:
     let elements = document.getElementsByClassName('hot')
     if (elements.length >= 1) {
        let firstItem = elements.item(0);
        }
        
     Array Syntax:
     let elements = document.getElementsByClassName('hot');
     if (elements.length >= 1) {
        let firstItem = elements[0];
        }
        
#### Repeating actions for an entire nodelist

When you have a NodeList you can loop through each node in the collection  <br>
And apply the same statements to each  <br>

Example Code:
        
        let hotItems = document.querySelectorAll('li.hot');
        for(let i = 0; i < hotItems.length; i++){
          hotItems[i].className = 'cool';
          }
          
#### Attribute Nodes
Once you have an element node  <br>
You can use other properties and methods on that element node <br>
that way you can access and change its attributes <br> 

Example Code:

     document.getElementById('one').getAttribute('class');
     
|Method|Description|
|:---:|:---:|
|get.Attribute()|gets the values of an attribute|
|has.Attribute()|checks if element node has an attribute|
|set.Attribute()|Sets the value of an attribute|
|removeAttribute()|Removes an attribtue from an element node|

 <br>
 <br>
  
|Property|Description|
|:---:|:---:|
|className|gets or sets value of the class attribute|
|id|gets or sets the value of the id Attribute|

### Summary of Chapter 5
- The browser represents the page using DOM tree
- DOM trees have four types of nodes:
  - document nodes
  - element nodes
  - attribute nodes
  - text nodes
- You can select element nodes by their
  - id
  - class attributes
  - tage name
  - CSS selector syntax
- Whenever a DOM query can return more than one node, it will always return a NodeList
- From an element node, you can access and update its content using properties such 
  - textContent
  - innerHTML
  - or DOM manipulation techniques
- An element node can contain multiple text nodes and child elements that are siblings of each other
- In older browsers, implementation of the DOM is inconsistent (and is popular reason for using jQuery)
- Browsers offer tools for viewing the DOM trees


