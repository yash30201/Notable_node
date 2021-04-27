---
pinned: true
tags: [node]
title: Node.Js
created: '2021-04-25T22:17:24.264Z'
modified: '2021-04-26T18:42:27.310Z'
---

# Node.Js

+ runs on chrome V8 engine
+ Allows javascript to run in a server by converting JS to machine code
+ Written in C++
---

#### Functions
 ```
  var temp = function(){
    // do something
  }
  temp(); // function fired!
  ``` 

---
#### Notes resumed
+ `require('./whatever')` allows to import different modules in other files
+ `module.exports = function_name` which we want to export
+ require returns the exproted object and we are required to get it in a var, `var f1 = require('/node1')`
+ we can export object like
  ```
    module.exports = {
      name1 : f1, 
      name2 : f2,
      name3 : var1
    }
  ```
   + and then get it like 
  ```
   var stuff = require('/adksmfl');
   stuff.f1();
   stuff.name3;
  ```



