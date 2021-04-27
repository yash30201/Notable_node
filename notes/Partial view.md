---
tags: [node/concept]
title: Partial view
created: '2021-04-27T05:38:08.876Z'
modified: '2021-04-27T05:48:24.932Z'
---

# Partial view
We can add partial views inside views in ejs files

`<%- include('partials/nav.ejs'); %>`
`<h1>Welcome</h1>`

and inside the partials directory of views there lies nav.ejs

*Take careful note of the syntax,* `<%- include('route inside views', {options obj})>`, *the starting hypen is a must!*
