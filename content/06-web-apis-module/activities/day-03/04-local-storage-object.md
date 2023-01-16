+++
title = "04. Local Storage Object 👩‍🎓👨‍🎓"
weight = 4
tags = ["web apis"] 
+++


# Local Storage with Objects

One of the most important skills a developer can learn is how to quickly research and find solutions to problems. Our application is attempting to store an object and not the data in it. Why?

## Instructions

* Find and implement a solution that allows the application to store and retrieve objects to and from `localStorage`.


**Hint:** You need to convert the object to a string, and vice versa.

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


### script.js
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
{{% /expand%}}
