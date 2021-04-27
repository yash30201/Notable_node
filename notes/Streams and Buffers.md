---
tags: [node/concept]
title: Streams and Buffers
created: '2021-04-26T18:53:37.704Z'
modified: '2021-04-27T04:25:00.988Z'
---

# Streams and Buffers

+ Buffer is a temporary storage area used to hold very small part of data untill the buffer is full and then it is transmitted as soon as buffer is filled and then buffer starts accepting next part of data and process repeats.
+ This increases the performance.

---

#### Types of streams
+ Writable streams
  + Allows writing in the stream
+ Readable streams
  + Allows to read from the stream.
+ Duplex
  + Allows both

---

```
var http = require('http');
var fs = require('fs');

var readStream = fs.createReadStream(__dirname + '/readme.txt' , 'utf-8');

readStream.on('data', function(chunk){
    console.log("New data chunk received");
    console.log(chunk);
})
```
- Evidently, readStream is like an event emitter and can run a dedicated function every time it receives a chunk of data.
- readFile reads whole file by itself in on go as compared to this.

---
+ We can also write chunks of read stream into write stream
```
var readStream = fs.createReadStream(__dirname + '/readme.txt' , 'utf-8');
var writeStream = fs.createWriteStream(__dirname + '/writeMe.txt');

readStream.on('data', function(chunk){
    console.log("New data chunk received");
    console.log(chunk);
    writeStream.write(chunk);
})
```
+ *But this method of using different read and write streams are big and we can do both easily using pipes with small code*
+ The above code can be simplified as
  + `readStream.pipe(writeStream);`
