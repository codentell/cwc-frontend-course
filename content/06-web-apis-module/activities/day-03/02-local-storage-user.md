+++
title = "02. Local Storage User 👩‍🎓👨‍🎓"
weight = 2
tags = ["web apis"] 
+++

# Local Storage

* You have been provided with a sign-up form that successfully submits an email and password. Your job is to write code that saves the email and password to `localStorage` and renders the last submission to the page.

## Instructions

* In your `signUpButton` event listener, you will need to:

  * Save the user to `localStorage`.

* In the `renderLastRegistered()` function, you will need to:

  * Fill in code here to retrieve the last registered credentials from `localStorage`.
  
  * If the last registered credential is null, return early from this function.
  
  * Else set the text of the `userEmailSpan` and `userPasswordSpan` to their corresponding values from `localStorage`.
  
**Hint:** Make sure you call `renderLastRegistered()` after you set your `localStorage`.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
###  index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="./style.css" />
    <title>Auth Form</title>
  </head>
  <body>
    <div class="clearfix">
      <div class="card">
        <h2>Sign Up</h2>
        <form method="POST">
          <div class="input-group">
            <label for="email">Email</label>
            <input type="text" name="email" id="email" placeholder="janedoe@mail.com" />
          </div>
          <div class="input-group">
            <label for="password">Password</label>
            <input type="password" name="password" id="password" placeholder="supersecure123" />
          </div>
          <div id="msg"></div>
          <button id="sign-up">Sign Up</button>
        </form>
      </div>

      <div class="card">
        <h2>Last Registered User:</h2>
        <p><strong>Email:</strong> <span id="user-email"></span></p>
        <p><strong>Password:</strong> <span id="user-password"></span></p>
      </div>
    </div>
    <script src="./script.js"></script>
  </body>
</html>
```

### script.js
```js
var emailInput = document.querySelector("#email");
var passwordInput = document.querySelector("#password");
var signUpButton = document.querySelector("#sign-up");
var msgDiv = document.querySelector("#msg");
var userEmailSpan = document.querySelector("#user-email");
var userPasswordSpan = document.querySelector("#user-password");


renderLastRegistered();

function displayMessage(type, message) {
  msgDiv.textContent = message;
  msgDiv.setAttribute("class", type);
}

function renderLastRegistered() {
  var email = localStorage.getItem("email");
  var password = localStorage.getItem("password");

  if (!email || !password) {
    return;
  }

  userEmailSpan.textContent = email;
  userPasswordSpan.textContent = password;
}

signUpButton.addEventListener("click", function(event) {
  event.preventDefault();

  var email = document.querySelector("#email").value;
  var password = document.querySelector("#password").value;

  if (email === "") {
    displayMessage("error", "Email cannot be blank");
  } else if (password === "") {
    displayMessage("error", "Password cannot be blank");
  } else {
    displayMessage("success", "Registered successfully");

    localStorage.setItem("email", email);
    localStorage.setItem("password", password);
    renderLastRegistered();
  }
});
Footer

```
{{% /expand%}}
