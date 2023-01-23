+++
title = "01. jQuery Elements 👩‍🏫🧑‍🏫"
weight = 1
tags = ["third party apis"] 
+++

{{< tabs >}}
{{% tab name="index.html" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">
  
<head>
  <meta charset="UTF-8" />
  <title>jQuery DOM elements</title>
  <link rel="stylesheet" href="./assets/css/jass.css" />
  <link rel="stylesheet" href="./assets/css/style.css" />

</head>

<body class="bg-dark text-light text-center">
  <!-- This empty `<div>` will anchor the elements we create with jQuery. -->
  <div class="m-5" id="root"></div>

  <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>

  <script type="text/javascript" src="./assets/js/script.js"></script>
</body>

</html>
```
{{% /tab %}}

{{% tab name="style.css" %}}
```css
.fancy {
  font-size: 60px;
  color: rgb(122, 242, 242);
  background-color: black;
  border-radius: 1rem;
  width: 380px;
  margin: 1rem auto;
}
```

{{% /tab %}}
{{% tab name="index.js" %}}
```js
// Comments show the vanilla JavaScript equivalent statements

// var rootEl = document.getElementById("root");
var rootEl = $('#root');

// var titleEl = document.createElement("h1");
var titleEl = $('<h1>');

// titleEl.textContent = "Hello friends";
titleEl.text('Hello friends');

// titleEl.className = 'fancy';
titleEl.attr('class', 'fancy');

// titleEl.classList.add('p-5') - (`p-5` is for padding)
titleEl.addClass('p-5');

// titleEl.style.border = "rgb(122, 242, 242) 3px solid";
titleEl.css('border', 'rgb(122, 242, 242) 5px solid');

// rootEl.appendChild(titleEl);
rootEl.append(titleEl);

// titleEl.append("Welcome to jQuery");
rootEl.append('<h2>With jQuery we can:</h2>');

var abilities = [
  'Select',
  'Create',
  'Style',
  'Animate',
  'Traverse',
  'Event Listen',
  'much more',
];

for (var i = 0; i < abilities.length; i++) {
  // Create a new `<div>` for each ability and its text content
  var abilityEl = $('<li>');

  // abilityEl.textContent = abilities[i];
  abilityEl.text(abilities[i]);

  // `my-3` class adds margin on top and bottom
  abilityEl.addClass('my-3');

  // Alternatively
  // var abilityEl = $("<div>" + abilities[i] + "</div>");

  // Add this new `<div>` to the abilities `<div>` container element.
  rootEl.append(abilityEl);
}

// select all `<div>` elements on the page
// document.querySelectorAll('div');
console.log($('div'));

// Alternatively use the `$.each` method
// $.each(abilities, function(i, ability) {
//    abilityEl.append("<div>" + ability + "</div>");
// })

```
{{% /tab %}}
{{< /tabs >}}



