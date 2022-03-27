# Readings: CRUD
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[Status Codes Based On REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)
In your own words, describe what each group of status code represents:

* 100’s = Informational status codes, tell a client that the header part of the request has been received
* 200’s = Success codes! tell the client the request was accepted. 
* 300’s = Redirection codes: tell the client that the resource they're requesting isn't available 
* 400’s = Client error codes, means the client sent an invalid request
* 500’s = Server error codes, means the server is overwhelmed or unreachable 
* What is a status code 202? 
  * Asynchronous processing of a request (met all validation requirements)
* What is a status code 308? 
  * Permanent redirect tells the client to use another URL to access the resource 
* What code would you use if an update didn’t return data to a client?
  * 204: no content for updates that don't return data to the client 
* What code would you use if a resource used to exist but no longer does?
  * 410 gone: we know the resource existed in the past but it got deleted or somehow moved. 
* What is the ‘Forbidden’ status code?
  * 403 Forbidden: client has authorized or doesn't need to authorize itself, still has no permissions to access the resource


Videos
[Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw) - First 20 minutes
* Why do we need to pull our MongoDB database string out of our server and put it into our .env?
  * because it's connecting to the mongoDB through our local server. once it's deployed you'll want to use something that isn't the localhost
* What is middleware?
  * code thats run when the server gets a request but before it gets passed to the route 
* What does app.use(express.json()) do?
  * express.json lets our server accept json as a body instead of the post element or get element
* What does the /:id mean in a route?
  * :id is a parameter which we can access whatever they pass in as a parameter 
* What is the difference between PUT and PATCH?
  * Patch only updates what the user passes us, put updates all the info all at once instead of just the info that's passed 
* How do you make a default value in a schema?
  * within the object you pass default as one of the keys and whatever you want the default to be as the value 
* What does a 500 error status code mean?
  * 500 error status means that something went wrong with our server and that it's not on the users side
* What is the difference between a status 200 and a status 201?
  * 200 means that everything is functioning as intended, 201 means that something was created successfully 

#### Video stream of thoughts notes
Build REST API quick
node.js express and mongodb
run npm init
enter a bunch for default values
creates package.json
install dependencies
npm i express (create app with nodejs) mongoose (interact with mongodb easy)
npm i --save-dev dotenv(pull in environment variables from a .env file) nodemon (refresh server everytime we make changes without having to manually exit and restart)
Remove "test" script in json
create own script called "devStart": "nodemon server.js"
touch server.js
touch .env
touch .gitignore
  ignore .env
  node_modules

back in server
const express = require('express') to pull in the express library
const app = express(); to create an app variable which can be used to configure the server 
app.listen(3001, () => console.log('server has started')) to listen to the port we're using and an arrow function to console log out that the server has started
npm run devStart works like nodemon because of the changes made in the json file, to start up the server 

configure mongoose to connect to the mongoDB database 
const mongoose = require('mongoose'); requires mongoose

mongoose.connect('mongodb://localhost/subscribers) this connects mongoose to mongodb and the server its run on (local for us) and the database name we choose (subscribers for the videos purpose)  
Saving this will give a deprecationWarning: current URL string parse is deprecated, and will be removed in the future, pass option { useNewUrlParser: true } to MongoClient.connect
So you can just take that option and pass it onto the end of the mongoose connect
mongoose.connect('mongodb://localhost/subscribers, { useNewUrlParser: true })
const db = mongoose.connection and here we can hook up some events to run when the DB is connected to
db.on('error, (error) => console.error(error))
db.once('open, () => console.log('Connected to DB'))

referencing back to line 62, we actually don't want that for when we launch the app since the local host will be different at that point so what he does is goes to his .env file and creates a variable
DATABASE_URL=mongodb://localhost/subscribers
then change whats on line 65 to match: 
mongoose.connect(process.env.DATABASE_URL, { useNewUrlParser: true })
this will throw an error which means you need to use the dotenv library 
so back up at the top you gotta require this
require('dotenv').config() this will load all the environment variables

so now all we gotta do is create routes and set up our server for json
first set up the server for json

app.use() this will allow us to use any middleware we want, code thats run when the server gets a request but before it gets passed to the route 
app.use(express.json())

const subscribersRouter = require('./routes/subscribers) so this will route all the subscriber info
So the next step is to create a new folder: routes and a file: subscribers.js
now tell the server that we want to use that route
app.use('/subscribers', subscribersRouter)
'localhost:3001/subscribers' will go into that router (the js file)

Within the subscribers js file
you'll need to require express again
and since you want the router portion of express you can just do
```js
const express = require('express')
const router = express.Router()
// Now create all the routes 
//getting all subs
router.get('/', (req, res) => {

})
//getting one
router.get('/:id', (req, res) => {
   
})
//creating one
router.post('/', (req, res) => {
  
})
//updating one
router.patch('/:id', (req, res) => {
  
})
//deleting one 
router.delete('/:id', (req, res) => {
  
})
module.exports = router
```
to test the rest api he's using an extension called REST client 
create file 
route.rest
in the file
```js 
GET http://localhost:3001/subscribers
-### <- this separates the requests
GET http://localhost:3001/subscribers/15
-### 
POST http://localhost:3001/subscribers
Content-Type: application/json

{
  "name": "Amazing Person"
  "subscribedToChannel": "Web Dev Simplified" 
}

``` 
now he's created a folder models
and is creating a subscriber scheme
it still uses the file type of js so you'll have two subscriber js file just within different files 

within the models subscriber js file
```js
const mongoose = require('mongoose')
const subscriberSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
  }.
  subscribedToChannel: {
    type: String,
    required: true,
  },
  subscribeDate: {
    type: Date,
    required: true,
    default: Date.now
  }
})
// name of model and the name of the schema
module.exports = mongoose.model('Subscriber', subscriberSchema)
```
head back to the subscriber js within the routes folder
and  add
```js
const Subscriber = require('../models/subscriber')
const express = require('express')
const router = express.Router()
// Now create all the routes 
//getting all subs
router.get('/', async (req, res) => {
  try {
    const subscribers = await Subscriber.find()
    res.json(subscribers)
  } catch (err){
    //500 means it's our fault not theirs
    res.status(500).json({ message: err.message})
    
  }
})
//getting one
router.get('/:id', (req, res) => {
   
})
//creating one
router.post('/', async (req, res) => {
  const subscriber = new Subscriber({
    name: req.body.name,
    subscribedToChannel: req.body.subscribedToChannel
  })
  try {
    const newSubscriber = await subscriber.save()
    res.status(201).json(newSubscriber) (201 means you successfully created!)
  } catch (err) {
    //400 means they did it not us
    res.stats(400).json({err.message})
  }
})
//updating one
router.patch('/:id', (req, res) => {
  
})
//deleting one 
router.delete('/:id', (req, res) => {
  
})
module.exports = router
```

## Things I want to know more about
I was thinking Schema's were for SQL but it seems like it's been used in this mongoDB tutorial, I'm curious to understand more about schemas