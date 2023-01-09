+++
title = "10. Timers Intervals 👩‍🎓👨‍🎓"
weight = 10
tags = ["web apis"] 
+++

# 📖 Create a Speed-Reader

Implement the following user story:

* As a developer, I want to create a speed-reading application that prints a single word of a message at a time.

## Acceptance Criteria

* It's done when the number of seconds left on the countdown is printed on the screen.

* It's done when, after the countdown of 5 seconds ends, the words of the message appear on the screen, one word at a time.

## 📝 Notes

Refer to the documentation: 

[MDN Web Docs on setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)

[MDN Web Docs on clearInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)

## Assets

The following animation demonstrates the web application's appearance and functionality:

![A countdown of 5 seconds begins and then single words appear on the screen.](./images/demo1.gif)

## 💡 Hints

How is `displayMessage()` utilizing the `setInterval()` and `clearInterval()` methods to display the words at an interval of 1000 milliseconds?

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* What `window` method is used to delay an action for a set number of milliseconds? Why might this method be useful?

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
    <title>Speed Reader</title>
    <link rel="stylesheet" href="./assets/css/style.css" />
  </head>
  <body>
    <div class="container">
      <h1 class="welcome">Welcome to Speed Reader</h1>
      <h2 id="countdown"></h2>
      <p id="main"></p>
    </div>
    <script src="./assets/js/script.js"></script>
  </body>
</html>
```
### script.js
```js
var timerEl = document.getElementById('countdown');
var mainEl = document.getElementById('main');

var message =
  'Some say the world will end in 🔥, Some say in ice. From what I’ve tasted of desire, I hold with those who favor fire. But if it had to perish twice, I think I know enough of hate. To say that for destruction ice, Is also great, And would suffice.';
var words = message.split(' ');

// Timer that counts down from 5
function countdown() {
  var timeLeft = 5;

  // Use the `setInterval()` method to call a function to be executed every 1000 milliseconds
  var timeInterval = setInterval(function () {
    // As long as the `timeLeft` is greater than 1
    if (timeLeft > 1) {
      // Set the `textContent` of `timerEl` to show the remaining seconds
      timerEl.textContent = timeLeft + ' seconds remaining';
      // Decrement `timeLeft` by 1
      timeLeft--;
    } else if (timeLeft === 1) {
      // When `timeLeft` is equal to 1, rename to 'second' instead of 'seconds'
      timerEl.textContent = timeLeft + ' second remaining';
      timeLeft--;
    } else {
      // Once `timeLeft` gets to 0, set `timerEl` to an empty string
      timerEl.textContent = '';
      // Use `clearInterval()` to stop the timer
      clearInterval(timeInterval);
      // Call the `displayMessage()` function
      displayMessage();
    }
  }, 1000);
}

// Displays the message one word at a time
function displayMessage() {
  var wordCount = 0;

  // Uses the `setInterval()` method to call a function to be executed every 1000 milliseconds
  var msgInterval = setInterval(function () {
    // If there are no more words left in the message
    if (words[wordCount] === undefined) {
      // Use `clearInterval()` to stop the timer
      clearInterval(msgInterval);
    } else {
      // Display one word of the message
      mainEl.textContent = words[wordCount];
      wordCount++;
    }
  }, 1000);
}

countdown();
```
{{% /expand%}}
