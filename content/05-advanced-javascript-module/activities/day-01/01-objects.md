+++
title = "01. Objects  👩‍🏫🧑‍🏫"
weight = 1
tags = ["advanced javascript"] 
+++

### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Objects</title>
</head>

<body>
  
  <h1 style="text-align:center">Open the Console to See the Magic ✨</h1>

  <script src="script.js"></script>

</body>
</html>
```

### script.js
```js
// Objects are a collection of properties
var planet = {
  // Properties are made up of key-value pairs
  name: "Earth",
  age: "4.543 billion years",
  moons: 1,
  isPopulated: true,
  population: "7.594 billion"
};

// To access a property's value that is a string, number or booleean, use the object's name and the associated key	
// Uses dot notation and logs "Earth"	
console.log(planet.name);
	
// Uses bracket notation and logs "Earth"
console.log(planet["name"]);
```
