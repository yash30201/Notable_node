---
tags: [node/modules]
title: Events and util
created: '2021-04-25T23:00:13.431Z'
modified: '2021-04-27T04:24:05.498Z'
---

# Events and util

### Event
Node.js has a built-in module, called "Events", where you can create-, fire-, and listen for- your own events.

*To include the built-in Events module use the require() method. In addition, all event properties and methods are an instance of an EventEmitter object. To be able to access these properties and methods, create an EventEmitter object:*

```
var events = require('events');

var emitter = new events.EventEmitter();
// Defining an event
emitter.on('someEvent', function(mssg){
    console.log(mssg);
});
// Emiting an event
emitter.emit('someEvent', {var1 : "tempo1", var2 : 40});
```

### Util 
 Allows objects to inherit other objects
```
var Person = function(name){
    this.name = name;
}
var util = require('util');
util.inherits(Person, events.EventEmitter);

var ina = new Person('Ina');
var mina = new Person('Mina');
var tina = new Person('Tina');
people = [ina, mina, tina];

people.forEach(person => {
    person.on('speak', function(mssg){
        console.log(person.name + " has spoken words of wisdom - \n ~ \""+ mssg + "\"");
    })
});

ina.emit('speak', "Tomorrow never dies");
```

