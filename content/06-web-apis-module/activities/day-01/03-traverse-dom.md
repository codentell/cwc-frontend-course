+++
title = "03. Traverse DOM  👩‍🏫🧑‍🏫"
weight = 3
tags = ["web apis"] 
+++

## index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DOM Traversal</title>
  <style>
      h1 {
        text-align:center;
      }
      ul {
        text-align:center;
        list-style-type:none;
        font-size: 40px;
        border: 10px solid blue
      }
  </style>
</head>

<body>
  <h1>Open the Console to See the Magic ✨! </h1>

  <ul>
    <li id ="first-child-ul">Children[0]</li>
    <li>Children[1]</li>
    <li>Children[2]</li>
  </ul>

  <script src= "script.js"></script>
</body>
</html>
```

## script.js
```js
console.log("Document Body: ")
console.log(document.body);

console.log("Children of Document Body: ")
console.log(document.body.children);

console.log("Second child of body: ")
console.log(document.body.children[1]);

console.log("First child of the ul: ")
console.log(document.body.children[1].children[0]);

// Accessing element by id
var firstChildUl = document.getElementById("first-child-ul");

// Setting style of element
firstChildUl.style.color = "#e97451";
```