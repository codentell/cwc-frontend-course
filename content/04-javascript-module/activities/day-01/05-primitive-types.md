+++
title = "05. Primitive Types 👩‍🎓👨‍🎓"
weight = 5
tags = ["javascript"] 
+++


```javascript
var one = 64;
var two = "656302";
var three = false;
var four = 64.55;
var five = "Howdy!";
var six;

// Insert comments to explain what each console log below will log to the console
console.log(typeof one); 
console.log(typeof two); 
console.log(typeof three); 
console.log(typeof four); 
console.log(typeof five);
console.log(typeof six);

four = "Hello!";
five = false;
six = 23;

// Insert comments to explain what each console log below will log to the console
console.log(typeof four);
console.log(typeof five);
console.log(typeof six);
```

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

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
var one = 64;
var two = "656302";
var three = false;
var four = 64.55;
var five = "Howdy!";
var six;

//Insert comments to explain what each console log below will log to the console
// Logs number
console.log(typeof one); 

// Logs string
console.log(typeof two); 

// Logs boolean
console.log(typeof three); 

// Logs number
console.log(typeof four); 

// Logs string
console.log(typeof five);

// Logs undefined
console.log(typeof six);

// Reassigns variables
four = "Hello!";
five = false;
six = 23;

// Insert comments to explain what each console log below will log to the console
// Logs string
console.log(typeof four);

// Logs boolean
console.log(typeof five);

// Logs number
console.log(typeof six);
```
{{% /expand%}}