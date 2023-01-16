+++
title = "09. Data Attributes 👩‍🏫🧑‍🏫"
weight = 9
tags = ["web apis"] 
+++

### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="./assets/css/style.css" />
    <title>Gif Player</title>
  </head>
  <body>
    <div class="img-container">
      <h1>Click on Image Below</h1>
      <!-- Save references to the image's animated and still versions as attributes on the element itself -->
      <img 
        src="https://media0.giphy.com/media/4Zo41lhzKt6iZ8xff9/200w_s.gif"
        data-animate="https://media0.giphy.com/media/4Zo41lhzKt6iZ8xff9/200w.gif"
        data-still="https://media0.giphy.com/media/4Zo41lhzKt6iZ8xff9/200w_s.gif"
        data-state="still" 
        alt="Funny dog flapping ears and tilting head side to side"
        />
      <img 
        src="https://media2.giphy.com/media/RQSuZfuylVNAY/200w_s.gif"
        data-animate="https://media2.giphy.com/media/RQSuZfuylVNAY/200w.gif"
        data-still="https://media2.giphy.com/media/RQSuZfuylVNAY/200w_s.gif"
        data-state="still"
        alt="Funny dog wearing superhero outfit walking on treadmill"
        />
      <img 
        src="https://media0.giphy.com/media/AGGz7y0rCYxdS/200w_s.gif"
        data-animate="https://media0.giphy.com/media/AGGz7y0rCYxdS/200w.gif"
        data-still="https://media0.giphy.com/media/AGGz7y0rCYxdS/200w_s.gif"
        data-state="still"
        alt="Funny baby excited about being presented with ice cream cone"
        />
      <img
        src="https://media2.giphy.com/media/vsGnvQD0ZcQco/200w_s.gif"
        data-animate="https://media2.giphy.com/media/vsGnvQD0ZcQco/200w.gif"
        data-still="https://media2.giphy.com/media/vsGnvQD0ZcQco/200w_s.gif"
        data-state="still"
        alt="Funny bird getting top of head brushed with toothbrush"
        />
    </div>
    <script src="./assets/js/script.js"></script>
  </body>
</html>
```

### script.js
```js
var imageContainer = document.querySelector(".img-container");

// Listen for any clicks within the img-container div
imageContainer.addEventListener("click", function(event) {
  var element = event.target;

  // Check if the clicked element was an image
  if (element.matches("img")) {
    // Get the current value of the image's data-state attribute
    var state = element.getAttribute("data-state");

    if (state === "still") {
      // Change the data-state attribute's value
      // There are two different ways this attribute can be set
      element.dataset.state = "animate";
      element.setAttribute("data-state", "animate");

      // Update the image's source to the string being stored in the data-animate attribute
      element.setAttribute("src", element.dataset.animate);
    } else {
      // Change the attributes back to their non-animated values
      element.dataset.state = "still";
      element.setAttribute("src", element.dataset.still);
    }
  }
});
```
