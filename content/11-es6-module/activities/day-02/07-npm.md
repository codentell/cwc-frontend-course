+++
title = "07. NPM 👩‍🏫🧑‍🏫"
weight = 7
tags = ["es6"] 
+++


```json
{
  "name": "12-Ins-npm-init",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "dependencies": {
    "badmath": "^1.0.1"
  },
  "devDependencies": {},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}

```



### index.js
```js
const badmath = require('badmath');

console.log(badmath.pie);

console.log(badmath.predictable());

```