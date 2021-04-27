---
tags: [node/concept]
title: Client server model
created: '2021-04-25T23:33:21.353Z'
modified: '2021-04-27T04:24:41.546Z'
---

# Client server model
Even at a particular server, many applications can run so how to identify my application?
 - By port numeber

---

+ We first instantiate a server then supply it with a function(req, res).
  + The req is the request our server recevives from the browser.
  + And res is the res obj to be sent out

```
var http = require('http');

var server = http.createServer(function(req, res){
    console.log('Request was made : ', req.url);
    res.writeHead(200, {'Content-type' : 'text/Plain'});
    res.end('Hey phantoms!');
});

server.listen(3000, '127.0.0.1');
console.log('Started');
```
+ If request is made like `127.0.0.1:3000/api/something`, then /api/somthing will be req.url.
+ Other formats of content-type are text/Plain, text/html, application/json, etc.
  + Json responses need to stringify their json response
    +  `res.end(JSON.stringify(myAns))`

+ Manual routes can be set up easily like `if(res.url === 'something'){} else{}`
+ express package help us with routing performing it efficiently and in a manageable manner
