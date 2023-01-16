+++
title = "05. Keyboard Events 👩‍🏫🧑‍🏫"
weight = 5
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
  <title>Font Checker</title>
  <link rel="stylesheet" href="./assets/css/style.css">
</head>

<body>
  <div class="container">
    <h1>Select serif or monospace</h1>
    <form>
      <select id="typeface">
        <option value="serif">
          serif
        </option>
        <option value="monospace">
          monospace
        </option>
      </select>
      <div style="margin-top: 50px;">
        <textarea id="textarea" placeholder="Your input" ></textarea>
        <div>
          <button id="clear">Clear</button>
        </div>
      </div>
    </form>
    <div class="elements">
      <h1 id="h1"></h1>
      <h2 id="h2"></h2>
      <h3 id="h3"></h3>
      <p id="p"></p>
    </div>
  </div>
  
  <script src="./assets/js/script.js"></script>
</body>
</html>
```

### script.js
```js
var typefaceEl = document.querySelector('#typeface');
var clearEl = document.querySelector('#clear');
var h1El = document.querySelector('#h1');
var h2El = document.querySelector('#h2');
var h3El = document.querySelector('#h3');
var pEl = document.querySelector('#p');
var textAreaEl = document.querySelector('#textarea');

var elements = [h1El, h2El, h3El, pEl];

var typeface;

// Change event
typefaceEl.addEventListener('change', function (event) {
  event.preventDefault();
  typeface = typefaceEl.value;
  document.querySelector('.container').style.fontFamily = typeface;
});

// Keydown event
textAreaEl.addEventListener('keydown', function (event) {
  // Access value of pressed key with key property
  var key = event.key.toLowerCase();
  var alphabetNumericCharacters = 'abcdefghijklmnopqrstuvwxyz0123456789 '.split(
    ''
  );
  if (alphabetNumericCharacters.includes(key)) {
    for (var i = 0; i < elements.length; i++) {
      elements[i].textContent += event.key;
    }
  }
});

clearEl.addEventListener('click', function (event) {
  event.preventDefault();
  textAreaEl.value = '';

  for (var i = 0; i < elements.length; i++) {
    elements[i].textContent = '';
  }
});
```