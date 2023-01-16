+++
title = "03. Local Storage Uh Oh"
weight = 3
tags = ["web apis"] 
+++

{{< tabs >}}
{{% tab name="index.html" %}}
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
            <label for="first-name">First Name</label>
            <input type="text" name="first-name" id="first-name" placeholder="Jane" />
          </div>
          <div class="input-group">
            <label for="last-name">Last Name</label>
            <input type="text" name="last-name" id="last-name" placeholder="Doe" />
          </div>
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
        <p><strong>First Name:</strong> <span id="user-first-name"></span></p>
        <p><strong>Last Name:</strong> <span id="user-last-name"></span></p>
        <p><strong>Email:</strong> <span id="user-email"></span></p>
        <p><strong>Password:</strong> <span id="user-password"></span></p>
      </div>
    </div>
    <script src="./script.js"></script>
  </body>
</html>
```
{{% /tab %}}
{{% tab name="style.css" %}}
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  font-size: 16px;
  font-family: "Roboto", sans-serif;
}

h2 {
  font-size: 3em;
  margin: 0px;
  margin-top: 0.45em;
  margin-bottom: 0.45em;
}

button {
  background-color: #039be5;
  border-radius: 8px;
  color: #fff;
  cursor: pointer;
  font-size: 1.2em;
  letter-spacing: 0.21px;
  line-height: 16px;
  max-width: 255px;
  padding: 20px 52px;
  text-align: center;
  transition-duration: 0.15s;
  transition-property: background-color;
  transition-timing-function: linear;
  margin-top: 0.6em;
  float: right;
}

button:hover {
  background-color: #0288d1;
}

.input-group {
  margin-top: 10px;
  margin-bottom: 10px;
}

label {
  color: #212121;
}

input {
  background-color: #f1f3f4;
  border-radius: 2px;
  border-width: 0;
  color: #5f6368;
  font-size: 1em;
  height: 45px;
  line-height: 20px;
  margin: 0;
  margin-top: 10px;
  max-width: 100%;
  padding: 8px 8px 8px 8px;
  transition-delay: 0s, 0s;
  transition-duration: 0.2s, 0.2s;
  transition-property: background-color, color;
  transition-timing-function: ease, ease;
  vertical-align: middle;
  width: 100%;
}

input:hover {
  background-color: #e8eaed;
}

.card {
  background-color: #fff;
  border: 1px solid #eceff1;
  border-radius: 8px;
  box-shadow: rgba(60, 64, 67, 0.3) 0 1px 2px 0,
    rgba(60, 64, 67, 0.15) 0 1px 3px 1px;
  margin: 2%;
  margin-top: 80px;
  padding: 20px;
  width: 46%;
  overflow: hidden;
  position: relative;
  float: left;
}

.card::after {
  content: " ";
  display: block;
  clear: both;
}

.clearfix::after {
  content: " ";
  display: block;
  clear: both;
}

#msg {
  visibility: hidden;
  margin-top: 20px;
  font-weight: 700;
  height: 1.2em;
  font-size: 1.2em;
}

#msg.success,
#msg.error {
  visibility: visible;
}

#msg.success {
  color: #52b155;
}

#msg.error {
  color: #e6252c;
}
```
{{% /tab %}}
{{% tab name="script.js" %}}
```js
var firstNameInput = document.querySelector("#first-name");
var lastNameInput = document.querySelector("#last-name");
var emailInput = document.querySelector("#email");
var passwordInput = document.querySelector("#password");
var signUpButton = document.querySelector("#sign-up");
var msgDiv = document.querySelector("#msg");
var userFirstNameSpan = document.querySelector("#user-first-name");
var userLastNameSpan = document.querySelector("#user-last-name");
var userEmailSpan = document.querySelector("#user-email");
var userPasswordSpan = document.querySelector("#user-password");

function displayMessage(type, message) {
  msgDiv.textContent = message;
  msgDiv.setAttribute("class", type);
}

signUpButton.addEventListener("click", function(event) {
  event.preventDefault();
  
  // create user object from submission
  var user = {
    firstName: firstNameInput.value.trim(),
    lastName: lastNameInput.value.trim(),
    email: emailInput.value.trim(),
    password: passwordInput.value.trim()
  };
  
  // validate the fields
  if (user.firstName === "") {
    displayMessage("error", "First name cannot be blank");
  } else if (user.lastName === "") {
    displayMessage("error", "Last name cannot be blank");
  } else if (user.email === "") {
    displayMessage("error", "Email cannot be blank");
  } else if (user.password === "") {
    displayMessage("error", "Password cannot be blank");
  } else {
    displayMessage("success", "Registered successfully");

    // set new submission
    console.log(user);
    localStorage.setItem("user", user);
    
    // get most recent submission
    var lastUser = localStorage.getItem("user");
    userFirstNameSpan.textContent = lastUser.firstName;
    userLastNameSpan.textContent = lastUser.lastName;
    userEmailSpan.textContent = lastUser.email;
    userPasswordSpan.textContent = lastUser.password;
  }
});
```
{{% /tab %}}
{{< /tabs >}}