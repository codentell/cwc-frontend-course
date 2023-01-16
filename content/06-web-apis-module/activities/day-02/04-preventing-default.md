+++
title = "04. Preventing Default 👩‍🎓👨‍🎓"
weight = 4
tags = ["web apis"] 
+++

# 🐛 Submit Button on Form Returns 404 Error

Work with a partner to resolve the following issues:

* Users should be able to see the calculated tip amount and total on the screen after clicking on the submit button. 

* Fix the code so that the actual behavior reflects the expected behavior

## Expected Behavior

When a user enters numbers in the text fields and clicks on the Calculate Tip button, calculated totals for both the tip amount and total should appear on screen.  

## Actual Behavior

When a user clicks on the Calculate Tip button, a 404 error appears. 

## Assets

The following image demonstrates the web application's appearance and functionality:

![The Tip Calculator app has returned a tip amount of 2.00 and a total of 12.00, for a meal cost of 10 and tip of 20%.](../images/01-screenshot.png)

---
## 💡 Hints

What action may be preventing the calculated totals from being rendered correctly on the page? How can we cancel that action?

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* Even when an event is canceled, it continues to propogate. What does that mean? 

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
  <title>Tip Calculator</title>
  <link rel="stylesheet" href="./assets/css/style.css">
</head>

<body>
  <div class="container">
    <h1>Tip Calculator</h1>
    <h3>Enter the total price of your meal below</h3>
    <form id="form">
      <input type="text" id="total" placeholder="total price of meal" />
      <input type="text" id="tip-percentage" placeholder="tip percentage" />
      <button id="submit">Calculate Tip</button>
    </form>
    <div class="tip-area">
      <h2>Tip amount: <span id="tip-amount"></span></h2>
      <h2>Total: <span id="new-total"></span></h2>
    </div>
  </div>

  <script src="./assets/js/script.js"></script>
</body>
</html>
```

### script.js
```js
var tipEl = document.querySelector("#tip-percentage");
var totalEl = document.querySelector("#total");
var submitEl = document.querySelector("#submit");

function calculateTip(total, tipPercentage) {
  var roundedResult = (total * tipPercentage).toFixed(2);
  return roundedResult;
}

function calculateTotal(total, tipAmount) {
  return parseFloat(total) + parseFloat(tipAmount);
}

function addTip(event) {
  // Prevent default action
  event.preventDefault();
  // Store tip and total calculations in variables
  var tipPercentage = tipEl.value * .01;
  var total = totalEl.value;
  var tipAmount = calculateTip(total, tipPercentage);
  var newTotal = calculateTotal(tipAmount, total);
  // Update HTML with tip and total
  document.querySelector("#tip-amount").textContent = tipAmount;
  // Use toFixed() to limit to two decimal places
  document.querySelector("#new-total").textContent = newTotal.toFixed(2);
}

// Add listener to submit element
submitEl.addEventListener("click", addTip);
```
{{% /expand%}}