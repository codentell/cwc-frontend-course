+++
title = "04. Click Events 👩‍🎓👨‍🎓"
weight = 4
tags = ["third party apis"] 
+++

# 🐛 Password Generator Doesn't Work on Single Click

Work with a partner to resolve the following issues:

* As a user, I should be able to click the "Generate Password" button.

* As a user, I should be able to single-click the "Generate Password" button to generate a new password.

* As a user, I should be able to generate a 15-character password upon click. 

## Expected Behavior

When a user single-clicks the "Generate Password" button, a 15-character password is printed to the page.

## Actual Behavior

When a user single-clicks the "Generate Password" button, nothing happens.

## Steps to Reproduce the Problem

1. Open `index.html` in the browser.

2. Click the "Generate Password" button to see that nothing happens.

## Assets

The following image demonstrates the web application's appearance and functionality:

![On the password generator app, an input field is filled by a random password.](../images/01-solution-screenshot.png)

---

## 💡 Hint 

* How can we ensure that our HTML elements have the correct event listeners attached to them?
  
## 🏆 Bonus 

If you have completed the activity and want to further your knowledge, work through the following challenge with your partner:

* What are alternate methods to add event listeners? Use [Google](https://www.google.com) or another search engine to answer this question.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <title>jQuery Password Generator</title>
    <link rel="stylesheet" type="text/css" href="./assets/css/jass.css" />
    <link rel="stylesheet" type="text/css" href="./assets/css/style.css" />
  </head>
  <body class="bg-dark text-light">
    <main>
      <h1>Password Generator</h1>
      <h2>Click on the button to get started!</h2>
      <hr/>

      <pre class="text-dark bg-light p-5" id="password-display">Password will go here...</pre>
      <button id="password-btn" class="btn btn-block btn-info ">Generate Password</button>
    </main>

    <!-- Added link to the jQuery library -->
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>

    <script type="text/javascript" src="assets/js/script.js" ></script>
  </body>
</html>
```

### index.js
```js
// Use the correct selector `#` to select a button by its ID and not class
var passwordBtnEl = $('#password-btn');
var passwordDisplayEl = $('#password-display');

// Function returns a random character that includes alphanumeric and special character values
function getPasswordCharacter() {
  return String.fromCharCode(Math.floor(Math.random() * 77) + 34);
}

// Function returns a string of concatenated characters of length num
function passwordGenerator(num) {
  var password = '';
  for (var i = 0; i < num; i++) {
    password += getPasswordCharacter();
  }
  return password;
}

// Change the event listener to `click` to make the event trigger on single-click
passwordBtnEl.on('click', function () {
  var newPassword = passwordGenerator(15);
  passwordDisplayEl.text(newPassword);
});
```
{{% /expand%}}