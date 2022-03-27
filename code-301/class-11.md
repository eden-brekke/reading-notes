# Readings: Mongo and Mongoose
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[nosql vs sql](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)
Fill in the chart below with five differences between SQL and NoSQL databases:


|SQL|NoSQL|
|:---:|:---:|
|Called as Relational Databases (RDBMS)| Called as non-relational or distributed databases|
|Table based Databases|Document based, key-value pairs, graph databases|
|Predefined schema|Dynamic schema|
|Vertically scalable|Scaled by increasing databases server in the pool or resources|
|Structured query language for defining and manipulating data|Queries are focused on collection of documents Unstructured query language|

* What kind of data is a good fit for an SQL database?
  * SQL databases are good for complex query intensive environments.
* Give a real world example.
  * MySQL community edition is an example of a SQL database. It's used for replication, and sharing 
* What kind of data is a good fit a NoSQL database?
  * Types of data to be stored, NoSQL databases fit better for data storage as it follows key-value pair way of storing data. 
* Give a real world example.
  * MonogoDB is an example of a NoSQL databsed, stores data in json like documents
* Which type of database is best for hierarchical data storage?
  * NoSQL
* Which type of database is best for scalability?
  * SQL

Bookmark/Skim <br>
[mongoose api](https://mongoosejs.com/docs/api.html#Model) <br>

[React Router](https://v5.reactrouter.com/web/api/BrowserRouter) <br>

Videos
[SQL vs NoSQL](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y) (Video)

* What does SQL stand for?
  * Structured Query Language
* What is a relational database?
  * SQL is a language that allows you to write database queries. A relational database works with certain assumptions and supports the SQL language
* What type of structure does a relational database work with?
  * they work with tables, a data bin so to speak 
* What is a ‘schema’?
  * defined by fields and its a certain type of data that goes into the DB. All records have to adhere to the schema, then you normalize the data by the schema. 
* What is a NoSQL database?
  * NoSQL is built to store lots and lots of data 
* How does it work?
  * There are databases that have collections of data and within the collections there are documents and they don't use a schema 
* What is inside of a Mongo database?
  * within the MongoDB are collections/documents that are similar to JSON files 
* Which is more flexible - SQL or MongoDB? and why.
  * MongoDB because it doesn't need to adhere to the strict schema format that SQL requires and no strict relations.  
* What is the disadvantage of a NoSQL database?
  * you can't be data you need for your build is within the database, you could also have some duplicate data, and if the info updates you might need to update it in more than one document 
  
## Things I want to know more about
I know we installed mongodb in our prework, will we also be using SQL in this class?