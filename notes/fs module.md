---
tags: [node/modules]
title: fs module
created: '2021-04-25T23:15:23.668Z'
modified: '2021-04-27T04:24:17.742Z'
---

# fs module

+ `var fs = require('fs') `
+ There are synchrounous as well as asynchronous(below code blocking / non blocking) methods
  + readFileSync
  + readMe
  + WriteFileSync
  + WriteFile

+ Read and write files

```
var fs = require('fs');

// Synchronous
var readme = fs.readFileSync('filename.txt', 'utf-8');
fs.writeFileSync('finename.txt', readme);

//  Asynchronous
fs.readFile('filename.txt', 'utf-8' ,fucntion(err, data){
    //do something
    //this function is run only when reading is completed
})

// but anything here will run while the file is being read
```

+ Removing files - `fs.unlink('name of the file to delete')`;
  + *Will give error if file doesn't exists*
+ Making directories - `mkdirSync('name of directory')`;
+ Removing directories - `rmdirSync('name of directory')`;
  + Their asynchronous ways are also there, `rmdir`, `mkdir`.

