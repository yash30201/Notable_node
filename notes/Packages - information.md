---
tags: [node/package-info]
title: Packages - information
created: '2021-04-27T04:12:33.560Z'
modified: '2021-05-07T06:46:06.067Z'
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
  + UPD - > No longer required as express again bundels a express.json() parser like
  + ```
    app.use(express.json());
    app.use(express.urlencoded({ extended: false }));
    ```
+ **Morgan** - (middleware),is an HTTP request logger middleware for Node.js that generates logs for each API request. The best part is that you can either use a predefined format or create a new one based on your needs.
  + morgan contains many predefined formats that you can use. Many developers prefer to use common, a standard Apache common log output.
+ **Helmet** - (middleware), is a security middleware that protects Express.js apps by setting various HTTP headers.
```
app.use(helmet());
//or
app.use(
    helmet({
        referrerPolicy: false,
    })
);
```
+ **CORS** - (middleware) , It is used to enable and configure CORS in Express.js apps.
  + *Imagine you have a full-stack app with a React frontend running on port 3000 and an Express backend server running on port 8000. A request comes from the client (i.e., the React frontend) to the backend Express server, but your request will most likely fail since it is coming from a different origin than the Express server.*
+ **Express rate limit** - (middleware), Express Rate Limit is a basic rate-limiting middleware for Express.js that, as the name suggests, limits the repeated API requests from the same IP address. For eg, In codeforces api, we can make only 5 requests per second from same ip address.
+ **serve-favicon** - is a favicon serving middleware. You may remember the failed favicon request when we opened the Network tab in the Helmet section.
+ **express-validator** - used to validate and format payload data in request object(like body, params, queries).
