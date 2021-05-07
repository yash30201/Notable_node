---
tags: [node/concept]
title: Middleware
created: '2021-04-27T06:40:01.516Z'
modified: '2021-05-03T14:11:51.458Z'
---

# Middleware
+ Its a piece of code having access to req and res and runs before a request is processed and after the response is created.
+ For example - 
```
app.use('/', function(req, res, next){
  //do something here
  next(); // goes to next middleware in the stack
  or 
  next('route') // goes to the next defined route
})
```
+ **!!!** If next(), is not written in middleware it will stop there and will not even execute the get request!
---
+ **It’s important to note that middleware tools are executed according to the order in which you define them.**
---
