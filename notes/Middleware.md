---
tags: [node/concept]
title: Middleware
created: '2021-04-27T06:40:01.516Z'
modified: '2021-04-27T06:59:23.779Z'
---

# Middleware
+ After a request starts and before it is served, all the things that happen is called middleware
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
