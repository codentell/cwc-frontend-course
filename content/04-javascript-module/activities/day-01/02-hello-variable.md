+++
title = "02. Hello Variable  👩‍🏫🧑‍🏫"
weight = 2
tags = ["javascript"] 
+++

### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hello Variable</title>
</head>

<body>
  
  <h1 style="text-align:center;">Open the Console to See the Magic ✨! </h1>

  <script src="script.js"></script>

</body>
</html>
```

### script.js
```javascript
// Declares student variable using var keyword 
var studentName;

// Uses assignment operator(=) to assign a value
var studentName = "Abdul";
var studentAge = 32;

// To re-assign a variable, use only the variable's name  
studentName = "Tonya";
studentAge = 52;

// To access a value stored in a variable, use the variable's name
console.log(studentName);

//To combine the message with a variable value use the concatenation operator(+)
//Logs "My name is "
console.log("My name is ");

// Logs "My name is Tonya"
console.log("My name is " + studentName);

```