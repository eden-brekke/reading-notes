# Reading

[What is Serverless Computing?]()
  * through the Pros and Cons section.

#### What is serverless?
Serverless is a could computing execution model
It automatically provisions the computing resources which are required to run application code on demand, or in response to an event. 
It automatically scales those resources in response to increase or decrease in demand 
and It automatically scales resources to zero when the application stops running 

Operation tasks: provisioning, scheduling, scaling, patch etc are offloaded to the cloud provider. 
Serverless only really describes the customer experience, as the servers still exist, but are managed by the cloud providers. 

#### Serverless vs FaaS (function as a service)
FaaS is a subset of serveless, it's a computing paradigm central to serverless, wherein application code or containers run only in response to events or requests.  
Serverless includes FaaS plus all the other associated resources and cloud services and resources supporting the code, storage databases, networks, API gateways, authentication, management and billing of services are invisible to the user 

#### Serverless pros and cons:
##### Pros
* enables dev team to focus on developing instead of managing ingrastructure. More time to innovate and optimize their front-end apps
* Serverless customers pay for execution only. Meter starts when the request is made and ends when execution finishes. 
* Serverless is a polyglot environment, meaning dev's can use any language they wish
* Simplifies DevOps cycles, Dev's don't have to describe infrastructure needed to integreate, test, deliver, and deploy the code
* Serverless can be faster and more cost effective for certain forms of compute
* serverless application development platforms provide near-total visibility into the system and user times. 

##### Cons
* Stable or predictable workloads: Does not offer same savings mentioned in pros when the workload is predictable/steady or long-running.
* Cold starts: need time to start up when they get a new request. 
* Teams may find it difficult or impossible to monitor or debug serverless functions using existing tools or processes
* Serverless architectures are designed to take advantage of an ecosystem of managed cloud serveres. For some companies deeply integrating with the cloud platform could be a risk

## Additional Resources

[venv - Creation of Virtual Environments]()

[Vercel - Get Started]()

[http.server]()

[Requests]()

[Python & APIs]()

## Videos

[What is Serverless?]()

### Bookmark and Review

[Serverless Functions]()

[Effective Python Environment]()