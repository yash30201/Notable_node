---
tags: [format, node]
title: Format for node
created: '2021-05-03T13:56:03.686Z'
modified: '2021-05-03T13:56:20.297Z'
---

# Format for node
```
const express = require("express");
const morgan = require("morgan")

const app = express();

// Middlewares
app.use(morgan("common"))


// Port
const port = 3000;

app.get("/", (req, res) => {
  res.json({
    message: "Hello Stranger! How are you?",
  });
});

// Listen
app.listen(port, ()=>{
    console.log(`Listening on port: ${port}`)
})
```
