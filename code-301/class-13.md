# Readings: More CRUD
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[CRUD Basics](https://medium.com/geekculture/crud-operations-explained-2a44096e9c88)

* Which HTTP method would you use to update a record through an API?
  * to update a record through an API you would use the "put" HTTP method (side note from previous video reading, you could use Patch to update 1 parameter of an object within the database whereas put will update everything)
* Which REST methods require an ID parameter?
  * get, put/patch, and delete require ID parameters 

Videos
[Speed Coding: Building a CRUD API](https://www.youtube.com/watch?v=EzNcBhSv1Wo) (Watch a Twitch streamer code an Express API in 20 minutes!)

* What’s the relationship between REST and CRUD?
  * REST apps usually use CRUD like functions. CRUD is create read update and delete whereas REST is Representational state transfer, an architectural style for software. 
* If you had to describe the process of creating a RESTful API in 5 steps, what would they be?
  1. install all your essentials 
  2. create your router/
  3. mount the router and check the CRUD get/put/delete routes
  4. create a schema to validate incoming data 
  5. Add things to the database! 


## Things I want to know more about