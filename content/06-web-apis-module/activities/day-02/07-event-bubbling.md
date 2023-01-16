+++
title = "07. Event Bubbling 👩‍🏫🧑‍🏫"
weight = 7
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
  <title>Document</title>
  <link rel="stylesheet" href="./assets/css/style.css">
</head>

<body>
  <div>
    <h2>Event Bubbling </h2>
    <div class="outer-div">CLICK TO TURN ME PURPLE
      <div class="inner-div">CLICK TO TURN ME ORANGE
        <div>
          <button class="button">CLICK TO TURN ME BLUE</button>
        </div>
      </div>
    </div>
  </div>
  
  <script src="./assets/js/script.js" ></script>
</body>
</html>
```

### script.js
```js
var outer = document.querySelector(".outer-div");
var inner = document.querySelector(".inner-div");
var button = document.querySelector(".button");

function changeBlue(event) {
  // event.stopPropagation();
  event.currentTarget.setAttribute(
    "style",
    "background-color: blue"
  );
}

function changePurple(event) {
  // event.stopPropagation();
  event.currentTarget.setAttribute(
    "style",
    "background-color: #601A4A"
  );
}

function changeOrange(event) {
  // event.stopPropagation();
  event.currentTarget.setAttribute(
    "style",
    "background-color: #EE442F; color: white;"
  );
}

outer.addEventListener("click", changePurple);
inner.addEventListener("click", changeOrange);
button.addEventListener("click", changeBlue);
```