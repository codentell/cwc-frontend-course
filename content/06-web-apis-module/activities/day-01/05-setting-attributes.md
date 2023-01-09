+++
title = "05. Setting Attributes 👩‍🏫🧑‍🏫"
weight = 5
tags = ["web apis"] 
+++


```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Setting Attributes</title>
    <link rel="stylesheet" href="./assets/css/style.css">
</head>
<body>
    <h1 class="title">Changing JS Attributes</h1>
    <section class="container">
    <a>
        <img>
    </a>
    <div>We use the .setAttribute() method to change attributes of elements on our page.</div>
    <p>We can change any element just by grabbing it via the DOM.</p>
    <div class="change1">We use .querySelectorAll() to select multiple elements at the same time.</div>
    <p id="change2">We can also grab elements using the id.</p>
    </section>

    <script src="assets/js/script.js"></script>
</body>
</html>

```

```js
// Access multiple elements using .querySelectorAll()
 var divTags = document.querySelectorAll("div");
 var pTags = document.querySelectorAll("p");
 var imgEl = document.querySelectorAll("img");

// Access element by ID using .querySelector()
 var changeP = document.querySelector("#change2");

// Sets first pTags to have a font-size of 40px
 pTags[0].setAttribute("style", "font-size: 40px;");

// Sets changeP to have multiple style attributes
 changeP.setAttribute("style", "font-size: 25px; font-weight: bold; text-decoration:underline; ");

 // Sets image source of the first image
 imgEl[0].setAttribute("src", "./assets/images/image_1.png");

// Adds size and width styling to image
 imgEl[0].setAttribute("style", "width:50%");

// Loops through divTags to set each one to have the color blue and the font size of 30px
for (var i = 0; i < divTags.length; i++) {
  divTags[i].setAttribute("style", "color:blue; font-size: 30px");
 }

```