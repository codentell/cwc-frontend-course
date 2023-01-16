+++
title = "01. Event Listener 👩‍🏫🧑‍🏫"
weight = 1
tags = ["web apis"] 
+++


### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Click Event</title>
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
</head>

<body>
  <div class="container dark">
    <div class="menu">
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#gallery">Gallery</a></li>
        <li><a href="#contact">Contact</a></li>
        <li><a href="#about">About</a></li>
      </ul>
    </div>
    <div class="row toggle">
      <div class="col">
        <p>DARK MODE</p>
      </div>
      <label class="switch col">
        <input type="checkbox" id="theme-switcher">
        <span class="slider round"></span>
      </label>
      <div class="col">
        <p>LIGHT MODE</p>
      </div>
    </div>
    <div class="row">
      <h2>Adding an Event Listener</h2>
    </div>
    <div class="row">
      <div>
        <p>We use the .addEventListener() method to set up an element to listen for a specific event</p>
        <p id= "light-mode">When we switch the slider to "Light Mode", the background is changed to a light color.</p>
        <p id = "dark-mode">When we switch the slider to "Dark Mode", the background is changed to a dark color.</p>
      </div>
      <div class="footer">
        <ul>
          <li><a href="#home">Terms of Use</a></li>
          <li><a href="#gallery">Privacy Policy</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="#about">About</a></li>
        </ul>
      </div>
    </div>

  <script src="./assets/js/script.js"></script>
</body>
</html>
```

### script.js

```js
// Access toggle switch HTML element
var themeSwitcher = document.querySelector("#theme-switcher");
var container = document.querySelector(".container");

// Set default mode to dark
var mode = "dark";

// Listen for a click event on toggle switch
themeSwitcher.addEventListener("click", function() {
  // If mode is dark, apply light background
  if (mode === "dark") {
    mode = "light";
    container.setAttribute("class", "light");
  }
  // If mode is light, apply dark background 
  else {
    mode = "dark";
    container.setAttribute("class", "dark");
  }
});
```

