+++
title = "04. Color Corrector 👩‍🎓👨‍🎓"
weight = 4
tags = ["third party apis"] 
+++

# Color Correcter Game

### Instructions

* For this activity, you'll be creating a "correct color" game.

* The game should generate a random color string (i.e., "green" or "blue") that is displayed in a random color. We'll cause this the current color.

* It should also generate a list of random color strings that are also displayed in random colors. We'll call this the color list.

* The user must click the *name* of the color in the color list that matches the *color* of the current color.

* Make an alert telling the user whether they chose correctly or incorrectly.

* After the alert, the game should reset.

* Check out the below GIFS to see how the game should work.

![correct color example](../images/correctColorExampleWin.gif)
![correct color example](../images/correctColorExampleLose.gif)

* **BONUS:** Make sure that none of the colors appear in the same color as their name.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
  <meta charset="UTF-8">
  <title>Correct Color Picker</title>

  <!-- Bootstrap File -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

  <!-- JQuery -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

  <style>
    #rand-target-color,
    #color-picker li {
      font-size: 24px;
    }
  </style>

</head>
<body>

  <div class="container">
    <h2>Correct Color Picker</h2>
    <p>Pick the <b>color</b> of the word shown from the list below it.</p>

    <div class="card">
      <div class="card-header">
        <h3 class="card-title">

          <!-- Create random target color -->
          <span id="rand-target-color">
          </span>

        </h3>
      </div>
      <div class="card-body">

        <!-- Create colors to pick -->
        <ul class="list-unstyled" id="color-picker">
        </ul>

      </div>
    </div>
  </div>

  <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript" src="./script.js"></script>
</body>
</html>
```

```js
// JavaScript function that wraps everything
$(document).ready(function() {

  // Array for word colors
  var colorsOfText = [];

  // Target word
  var targetColor;

  // Target word color
  var targetColorOfText;

  // User"s selection
  var userAnswer;

  // Array for words
  var colors = [
    "brown",
    "blue",
    "magenta",
    "teal",
    "coral",
    "black"
  ];

  // This function sets a random color "word" and a random set of colors "visuals"
  function randColor() {

    // Set random word
    targetColor = colors[Math.floor(Math.random() * colors.length)];
    $("#rand-target-color").text(targetColor);

    // Set random word color
    targetColorOfText = colors[Math.floor(Math.random() * colors.length)];
    $("#rand-target-color").css("color", targetColorOfText);
  }

  // This function creates the actual "game" logic.
  function createColorPicker() {

    // Shuffle color array
    colors.sort(function() {
      return 0.5 - Math.random();
    });

    // Push to text color array
    for (var i = 0; i < colors.length; i++) {
      colorsOfText.push(colors[i]);
    }

    // Shuffle text color array
    colorsOfText.sort(function() {
      return 0.5 - Math.random();
    });

    // Loop through all colors in the array
    for (var i = 0; i < colors.length; i++) {

      // Create element to hold word
      var holder = document.createElement("li");
      $("#color-picker").append(holder);

      // Output a word
      $(holder).attr("id", colors[i]).text(colors[i]);

      // Make word a random color
      $(holder).css("color", colorsOfText[i]);
    }
  }

  // Clear the divs and arrays upon each round.
  function clear() {
    $("#rand-target-color").empty();
    $("#color-picker").empty();
    colorsOfText = [];
  }

  // Function for resetting colors and setting new colors.
  function reset() {
    clear();
    randColor();
    createColorPicker();
  }

  // Get id of element clicked by user
  $("#color-picker").click(function(event) {
    userAnswer = event.target.id;

    // Compare id to target id
    if (userAnswer === targetColorOfText) {
      alert("You win!");
      reset();
    }
    else {
      alert("Wrong!");
      reset();
    }
  });

  // Run game
  reset();
});

```
{{% /expand%}}