+++
title = "05. Modularization 👩‍🏫🧑‍🏫"
weight = 5
tags = ["es6"] 
+++

### badmath.js
```js
const pie = 'apple';

const predictable = () => 1;

// module.exports is an object we use to store variables or methods
module.exports = {
  pie,
  predictable,
};
```

### index.js
```js
const badmath = require('./badmath.js');

console.log(badmath.pie);

console.log(badmath.predictable());
```