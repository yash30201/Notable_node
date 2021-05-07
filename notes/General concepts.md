---
tags: [node/concept]
title: General concepts
created: '2021-05-03T14:14:20.909Z'
modified: '2021-05-03T14:15:24.517Z'
---

# General concepts
+ [app.listen vs server.listen](https://stackoverflow.com/questions/17696801/express-js-app-listen-vs-server-listen)
+ A callback is a function passed as an argument to another function.
```
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}

function myCalculator(num1, num2, myCallback) {
  let sum = num1 + num2;
  myCallback(sum);
}

myCalculator(5, 5, myDisplayer);
```


