---
tags: [node/chatapi]
title: ChatAPi general notes
created: '2021-05-03T13:52:50.122Z'
modified: '2021-05-03T17:54:48.420Z'
---

# ChatAPi general notes
+ Create directory, initiate npm, install necessary modules - 
  + (later) express, mongoose, uuid, jsonwebtoken, morgan, socket.io, @withvoid/make-validation
+ In package.json file of node, there's an argument **script**. It allows us to write and access CLI code with just npn run scriptname, for eg,
  + to run `nodemon server/index.js`, we just do `npm run start`, simply insert the key of that command. 
```
"scripts": {
	"start": "nodemon server/index.js",
	"start:server": "node server/index.js"

  //ingeneral
  "start": "node index.js",
  "dev": "nodemon index.js"
},
```
+ Create a server directory, and cd into it and do things here
+ Basic structure is to first place proper middlewares in sequence the place proper routers in sequence, then place a error handler to handel all the errors like this - 
```
app.use('*', (req, res) => {
  return res.status(404).json({
    success: false,
    message: 'API endpoint doesnt exist'
  })
})

// or try this

//Lower middlewares
app.use(function(err, req, res, next){
    res.status(422).send({
        error : err.message
    });
});
```
+ This is how then server is created - 
  + In upper echelon, port is defined
    + `const port = process.env.PORT || "3000";`
  + In lower echelon server is created and set up
    + ```
      const server = http.createServer(app);
      server.listen(port);
      /** Event listener for HTTP server "listening" event. */
      server.on("listening", () => {
        console.log(`Listening on port:: http://localhost:${port}/`)
      });
      ```
