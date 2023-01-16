+++
title = "10. Data Attributes 👩‍🎓👨‍🎓"
weight = 10
tags = ["web apis"] 
+++

# 🏗️ Use Data Attributes to Display Hidden Number

* As a player, I want to click on a card and view the hidden number.

## Acceptance Criteria

* It's done when I click on a card and the hidden number is revealed.

* It's done when the number is visible if the card is clicked.

## Assets

The following image demonstrates the web application's appearance and functionality:

![Six cards appear in a grid, with the numbers 1, 3, and 5 displayed on three of the cards while the remaining three appear blank.](../images/02-screenshot.png)

---

## 💡 Hints

How can we use the `dataset` object to access an element's data attributes? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* We have learned `getAttribute()` and `setAttribute()`. What other methods can you use to access an element's attributes? 

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="./assets/css/style.css" />
    <title>Data Attributes</title>
  </head>
  <body>
    <h1>Click on Box to Show Hidden Number</h1>
    <div class="container">
      <div class="box" data-number="1" data-state="hidden"></div>
      <div class="box" data-number="2" data-state="hidden"></div>
      <div class="box" data-number="3" data-state="hidden"></div>
      <div class="box" data-number="4" data-state="hidden"></div>
      <div class="box" data-number="5" data-state="hidden"></div>
      <div class="box" data-number="6" data-state="hidden"></div>
  
    <script src="./assets/js/script.js"></script>
  </body>
</html>
```

### script.js
```js
var container = document.querySelector(".container");

container.addEventListener("click", function(event) {
  var element = event.target;

  if (element.matches(".box")) {
    var state = element.getAttribute("data-state");

    // Use an if statement to conditionally render the number on the card
    if (state === "hidden") {
      // If the card is clicked while the state is "hidden", we set .textContent to the number 
      element.textContent = element.dataset.number;
      // Using the dataset property, we change the state to visible because the user can now see the number
      element.dataset.state = "visible";
   
    } else {
      // 'Hide' the number by setting .textContent to an empty string
      element.textContent= "";
      // Use .setAttribute() method
      element.setAttribute("data-state", "hidden")
     
    }  
  }
  
});
```
{{% /expand%}}