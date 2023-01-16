+++
title = "06. Keyboard Events 👩‍🎓👨‍🎓"
weight = 6
tags = ["web apis"] 
+++


# 📖 Implement Keyboard Events to Display Value and Code of Pressed Key

Work with a partner to implement the following user story:

* As a developer, I want to display the value and code of a pressed key.

## Acceptance Criteria

* It's done when, if a key is pressed down, the value of the key and the key's code is displayed. `KEYDOWN Event` should also be displayed to indicate the type of event. 

* It's done when, if the key is released, `KEYUP Event` is displayed.

## 📝 Notes

Refer to the documentation: 

[MDN Web Docs on keyup](https://developer.mozilla.org/en-US/docs/Web/API/Document/keyup_event)

[MDN Web Docs on keydown](https://developer.mozilla.org/en-US/docs/Web/API/Document/keydown_event)

## Assets

The following image demonstrates the web application's appearance and functionality:

![The web app includes lines to display "Key Pressed", "Key Code", and "Event status".](./images/01-screenshot.png)

---

## 💡 Hints

What properties can we use to access the value of the pressed key and the key's code?

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What other properties can you access using the `KeyboardEvent` object? 

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
  <title>Keyboard Events</title>
  <link rel="stylesheet" href="./assets/css/style.css">
</head>

<body>
  <div class="container">
    <div id="key-events">
      <div id= "title">
        <h2>keydown ⬇️ and keyup ⬆️ </h2>
        Key Pressed : <span id="key"></span>
      </div>
      <div>
        Key Code : <span id="code"></span>
      </div>
      <div>
      Event status : <span id="status"></span>
      </div>
    </div>
  </div>

  <script src="./assets/js/script.js"></script>
</body>
</html>
```

### script.js
```js
function keydownAction(event) {
  // The key property holds the value of the key press
  var keyPress = event.key;
  // The code property holds the key's code 
  var keyCode = event.code;
  // Updates content on page
  document.querySelector("#key").textContent = keyPress;
  document.querySelector("#code").textContent = keyCode;
  document.querySelector("#status").textContent = "KEYDOWN Event";
}

function keyupAction() {
  // Updates event to KEYUP Event when key is released
  document.querySelector("#status").innerHTML = "KEYUP Event";
}
// Adds listener for keydown event
document.addEventListener("keydown", keydownAction);
// Adds listener for keyup event
document.addEventListener("keyup", keyupAction);
```
{{% /expand%}}