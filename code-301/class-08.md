# Readings: APIs
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

* What does REST stand for?
  * REST Stands for Representational State Transfer
* REST APIs are designed around a ____.
  *  resources, a kind of object, data or service that the client can access 
* What is an identifer of a resource? Give an example.
  * the URL that uniquely identifies that resource, can be HTTP:?? or json data
* What are the most common HTTP verbs?
  * Most common are GET POST PUT PATCH DELETE
* What should the URIs be based on?
  * Consistent naming convention and a heirarchy
* Give an example of a good URI.
  * should not be more than 3 resources deep
* What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
  * Chatty APIs are good and bad, data retrieval comes in smaller waves, can cause a loan on the server, but a single request risks sending unwanted data and increasing bandwidth used
* What status code does a successful GET request return?
  * HTTP STATUS 200 OK
* What status code does an unsuccessful GET request return?
  * 404 - NOT FOUND
* What status code does a successful POST request return?
  * HTTP STATUS 201 CREATED
* What status code does a successful DELETE request return?
  * HTTP status CODE 204 

## Bookmark/Skim
[RegExr](https://regexr.com/) - Pay particular attention to the cheatsheet

* How would you match a phone number from your city using RegEx?

[Regex Tutorial](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)
[Regex 101](https://regex101.com/)


## Things I want to know more about