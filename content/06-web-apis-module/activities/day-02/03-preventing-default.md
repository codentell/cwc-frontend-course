+++
title = "03. Preventing Default 👩‍🏫🧑‍🏫"
weight = 3
tags = ["web apis"] 
+++

### index.html 

```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Event Prevent Default Demo</title>
  <link rel="stylesheet" href="./assets/css/style.css">
</head>

<body>
  <div class="wrapper">
    <div class="container">
      <div class= "card-contents"></div>
        <h1>Contact Page</h1>
        <form>
          <input placeholder="name" id="name" />
          <input placeholder="email" id="email" />
          <button id="submit">Submit</button>
          <div>
            <h3 id="response"></h3>
          </div>
        </form>
      </div>
    </div>
  </div>

  <script src="./assets/js/script.js"></script>
</body>
</html>
```

### script.js
```js
var submitEl = document.querySelector("#submit");
var nameInput = document.querySelector("#name");
var emailInput = document.querySelector("#email");
var submissionResponseEl = document.querySelector("#response");

// Action to be performed on click store in named function
function showResponse(event) {
  // Prevent default action
  event.preventDefault();
  console.log(event);
  var response = "Thank you for your submission " + nameInput.value + "! We will reach out to you at " + emailInput.value + ".";
  submissionResponseEl.textContent = response;
}
  
// Add listener to submit element
submitEl.addEventListener("click", showResponse);
```