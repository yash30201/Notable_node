---
tags: [node/modules, post request]
title: Express
created: '2021-04-27T04:27:01.143Z'
modified: '2021-04-27T08:20:23.298Z'
---

# Express

```
var express = require('express');
//It is a function, so
var app = express();
app.listen(portnumber);
```
+ app.get('route', func(req, res));
+ app.put('route', func(req, res));
+ app. post('route', func(req, res));
+ app.delete('route', func(req, res));
```
app.get('/', function(req, res){
    res.send('This is my homepage');
})
```
+ Dynamic get requests
```
app.get('/profile/:id', function(req, res){
    res.send('You have requested information regarding person of id : ' + req.params.id);
})
```

+ Sending methods
  + send
  + sendFile
---
### We can use EJS module to inject javascript code into html, see package-info for more intro
+ the app.js get request
```
    app.get('/profile/:id', function(req, res){
      data = [1, 24, 5, 2, 2, 1, 2];
      res.render('profile', {person : req.params.id, data : data});
    })
 ```
+ the profile.ejs file
```
    <p>You are viewing profile with id : <%= person%></p>
    <br />
    <ul>
        <% data.forEach(function(item){ %>
            <li><%= item %></li>
        <% }) %>
    </ul>
```
---
### Express.static()
+ We can use express.static() to get the static files like css 
+ Syntax - `app.get(express.static('directory'))` if we want to treat all requests as same
+ Syntax - `app.get('virtual_route', express.static('directory'))` if we want to reply to virtual_route requests only
---
### Query strings
+ In express, the req onject does the parsing all by itself and we get access the query obj by req.query
---
### Post requests
+ Suppose we have a form, then we just have to edit method field to POST and action to the post request handle route.
  + `<form id="contact-form" action="/contact" method="post">`
+ Now ,we just create an app.post() handler for the route defined in action
```
app.post('/contact',urlEncodingParser,  function(req, res){
    console.log(req.body);
    res.render('contact-success', {data: req.body});
})
```


