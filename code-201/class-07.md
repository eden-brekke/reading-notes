# Class 07 Reading Notes

## Article [Domain Modeling](https://github.com/codefellows/domain_modeling#domain-modeling)

#### Domain Modeling
 Domain modeling is the act of creating a conceptual model in code for a problem. <br>
 Object-oriented Model: stores data iin properties and encapsulates behaviors <br>
 
#### Model Epic Fail Videos
Task: build a program the models the popularity of epic fail videos <br>
two essential metrics: <br>
1. epic rating
2. whether or not video has animals

Representation of EpicFailVideo object: <br>

|Property|Data|Type|
|:---:|:---:|:---|
|epicRating|1 to 10|Number|
|hasAnimals|true or false|Boolean|

    let = EpicFailVideo = function(epicRating, hasAnimals){
      this.epicRating= epicRating;
      this.hasAnimals = hasAnimals;
     }
     
     let parkourFail = new EpicFailVideo(7, false);
     let corgiFail = new EpicFailVideo(4, true);
     
     console.log(parkourFail);
     console.log(corgiFail);


The keyword "new" creates a new object <br>
The constructor function initializes properites inside the object using the this vairbale <br>
the object is stored in a variable for later use <br>

     let = EpicFailVideo = function(epicRating, hasAnimals){
      this.epicRating= epicRating;
      this.hasAnimals = hasAnimals;
     }
     
     EpicFailVideo.prototype.generateRandom = function(min, max){
        return Math.floor(Math.random() * (max - min +1)) + min;
       }
       
       let parkourFail = new EpicFailVideo(7, false);
     let corgiFail = new EpicFailVideo(4, true);
     
     console.log(parkourFail.generateRandom(1, 5));
     console.log(corgiFail.generateRandom(1,5));
     
Think of prototype as the objects stunt double. <br>
takes longer to locate prototype <br>

#### Calculate daily likes

      let = EpicFailVideo = function(epicRating, hasAnimals){
      this.epicRating= epicRating;
      this.hasAnimals = hasAnimals;
     }
     
     EpicFailVideo.prototype.generateRandom = function(min, max){
        return Math.floor(Math.random() * (max - min +1)) + min;
       }
       
       EpicFailVideo.prototype.dailyLikes = function(){
        let viewers, percentage;
        
        viewers =  this.generateRandom(10, 30) * this.epicRating
        
        if(this.hasAnimals){
        percentage = 0.75;
        }else{
        percentage = 0.40;
        }
        return Math.round(viewers*percentage);
       }
       
       // Now for weekly:
       let total = 0; 
       for (let i = 0; i < 7; i++)
            total += this.dailyLikes();
          }
          return total;
       }
     let parkourFail = new EpicFailVideo(7, false);
     let corgiFail = new EpicFailVideo(4, true);
     
     console.log(parkourFail.daily/weeklyLikes());
     console.log(corgiFail.daily/weeklyLikes());

#### Summary

Domain modeling is the process of creating a conceptual model for a problem. <br>
Tips:
1. when modeling a single entity that'll have many instance, build self-contained objects with the same attribute and behaviors
2. model its attributes with a constructor function that defines and initializes properties
3. model its behaviors with small methos that focus on doing one job well
4. create instances using the new keyword followed by a call to a constructor function
5. store the newly created object in a variable so you can access its properties and methods from outside
6. Use the this variable within methods so you can access the objects properties and methods from inside.
       
       
## HTML and CSS Chapter 6 pg 126-145

### Key Topics
- How to create tables
- What information suits tables
- How to represent complex data in tables

#### What is a table
Tables represent info in a grid format. <br>
each block in a grid is called a 'table cell' 

Some html tags for tables:
     
     <table> create a table
     <tr> start of a row
     <td> cell of a table
     <th> heading of a column or a row
     <thead> heading of table
     <tbody> body of table
     <tfoot> footer of table

### Chapter 6 Summary
- The table element is used to add tables to a webpage
- A table is drawn out row by row. Each row is created with tr
- inside each row there are a number of cells represented by the td element (or th if its header)
- you can make cells of a table span more than one row or column using the rowspan and colspan attributes
- for tables you can split them into thead tbody and tfoot



## JavaScript and jQuery Chapter 3 pg 106-144

#### Creating an object: constructor Notation
      let hotel - newObject();
        hotel.name = '';
        hotel.rooms = 40;
        hotel.booked = 25;
        hotel.checkAvailability=function(){
          return this.room - this.booked;
          };
          
#### Updating an Object
To update a value of propterties you can use dot notation or square brackets. 
        
        hotel.name = '';
        or 
        hotel['name']='';

#### Creating many objects: constructor Notation
sometimes you will want several objects to represent similar things. <br>
object constructors can use a function as a template for creating objects. <br>

      function hotel(name, rooms, booked) {
      this.name = name;
      this.rooms = rooms;
      this.booked = booked;
      this.checkAvailability =function(){
          return this.room - this.booked;
          };
        
 You create instances of the object using the constructor function. <br>
 new keyword followed by a call to the function creates a new object <br>
 the properties of each object are given as arguments to the function <br>
 
        let QuayHotel = new Hotel('Quay', 40, 25);
        let parkHotel = new Hotel('Park', 120, 77;
        
  
#### Arrays are objects and objects in arrays
Arrays are actually a special type of object <br>
they hold a related set of key/value pairs and each value is given an index number. <br>
You can combine arrays and objects to create complex data structures. <br>
arrays can store a series of objects <br>
objects can also hold arrays. <br>

#### Three groups of built in objects
Browser object model: creats a model of browser tab or window <br>
Document object model: (DOM) creates a model of current webpage <br>
global JS object: do not form a single model. but are a group of individual objects that relate to different parts of the JS language <br>

#### Creating an instance of date object
In order to work with dates you create an instance of the Date object <br>
you can then specify the time and date that you want it to represent
  
      let today = new Date();

### Chapter 3 Summary 
- An object is a series of variables and functions that represent soething from the world around you
- in an object variables are known as properties of the object (called methods)
- web browsers implement objects that represent both the browser window and the document loaded into the browser window
- JS also have several built-in objects such as String, Number, Math, and Date. their properties an methods offer functionality that help you write scripts.
- arrays and objects can be used to create complex data sets (and both can contain the other) 
