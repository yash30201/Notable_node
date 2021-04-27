---
tags: [node/package-info]
title: Packages - information
created: '2021-04-27T04:12:33.560Z'
modified: '2021-04-27T08:19:15.622Z'
---

# Packages - information

+ **Nodemon** - Watches for any changes in files so as to automatically restart the node server, perfect while developing a server!
  + Since this is only required during development phase, so its better to install this package globally!

+ **ejs** - Allows us to inject javascript in html responses to create templates and dynamic responses
  + After installing we need to tell express that we need to use ejs `app.set('view engine', 'ejs')`
  + By default, ejs view looks for a directory names views in home directory to check for pages
  + The extension is .ejs
  + res.render('route', {})
    + 'route' is the view name in views directory
    + {} = > object of options which we send to _viewname.ejs
    + `{name : res.params.name, age : res.params.age} ` - in app.js
    + ` <%= name %>` in ejs file

+ **body-parser** - Allows us to parse body , for eg form data during post method
