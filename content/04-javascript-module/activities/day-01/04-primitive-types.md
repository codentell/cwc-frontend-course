+++
title = "04. Primitive Types  👩‍🏫🧑‍🏫"
weight = 4
tags = ["javascript"] 
+++

### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Primitive Types</title>
</head>

<body>
  
  <h1 style="text-align:center;">Open the Console to See the Magic ✨! </h1>

  <script src="script.js"></script>

</body>
</html>
```


### script.js
```javascript
//Primitive data types include undefined, string, number and boolean
//Undefined variables haven't been assigned values yet.
var myUndefined;

// A string is a series of characters and is surrounded by quotes 
var myStringWelcome = "Hello World"; 
var myStringPassword = "865Password!2020";

// A number can be either an integer or a decimal  
var myNumberInt = 100;
var myNumberDecimal = 100.100;

// Booleans have two values: true or false
var isMyBooleanTrue = true;
var isMyBooleanFalse = false;

// To check the type of data, use typeof followed by the name of the variable
// Logs undefined
console.log(typeof myUndefined);

// Logs number
console.log(typeof myNumberInt); 

// Logs boolean
console.log(typeof true);

// Logs string
console.log(typeof "Howdy");

// Pro-tip: JavaScript is loosely typed, so the type is tied to the value held in the variable, not the variable itself!
// Logs number
var myVariable = 33;
console.log(typeof myVariable);

// myVariable is reassigned; Logs boolean
myVariable = false;
console.log(typeof myVariable);
```