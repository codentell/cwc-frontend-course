+++
title = "02. Event Listener 👩‍🎓👨‍🎓"
weight = 2
tags = ["web apis"] 
+++

# 🏗️ Implement Event Handler on Mouse Click

Work with a partner to implement the following user story:

* As a developer, I want to increment or decrement a count when a user clicks on a button.

## Acceptance Criteria

* It's done when a user clicks on the increment button and the count is increased by `1`.

* It's done when a user clicks on the decrement button and, if the count is greater than `0`, the count is decreased by `1`.

## Assets

The following animation demonstrates the web application's appearance and functionality:

![As the user selects the Decrement and Increment buttons, the Current Count number decreases and increases respectively.](../images/01-demo.gif)

---

## 💡 Hints

What method can we use to listen for an mouse click? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* A click is just one type of DOM event. What are some others?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Click Counter</title>
  <link rel="stylesheet" href="./assets/css/style.css">
</head>

<body>
  <div class="wrapper">
    <div class="container">
      <div class="card-contents" >
        <h4>Current Count: <span id="count">0</span></h4>
        <button id="decrement">Decrement</button>
        <button id="increment">Increment</button>
      </div>
    </div>
  </div>
  
  <script src="./assets/js/script.js"></script>
</body>
</html>
```
### script.js
```js
var count = 0;
//  Select increment and decrement button elements
var incrementEl = document.querySelector("#increment");
var decrementEl = document.querySelector("#decrement");
var countEl = document.querySelector("#count");

// Updates count on page
function setCounterText() {
  countEl.textContent = count;
}
// Attach event listener to increment button element
incrementEl.addEventListener("click", function() {
  count++;
  setCounterText();
});

// Attach event listener to decrement button element
decrementEl.addEventListener("click", function() {
  // Action will fire if count is greater than  0
  if (count > 0) {
    count--;
    setCounterText();
  }
});
```
{{% /expand%}}
