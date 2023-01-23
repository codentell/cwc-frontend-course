+++
title = "05. Form Elements 👩‍🏫🧑‍🏫"
weight = 5
tags = ["third party apis"] 
+++


{{< tabs >}}
{{% tab name="index.html" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8" />
  <title>jQuery Pizza</title>
  <link rel="stylesheet" type="text/css" href="./assets/css/jass.css">
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
</head>

<body>
  <div class="bg-dark min-100-vh flex-row align-center justify-center">
    <div class="col-11 col-sm-8">
      <h1 class="text-light">Free Pizza Raffle Sign Up!</h1>

      <div class="card rounded bg-light p-3">
        <div class="card-body">
          <form id="pizza-form">
            <div class="row">
              <div class="col-12 col-sm-6">
                <label for="first-name">First Name</label>
                <input type="text" class="form-input" name="first-name" placeholder="Enter first name" />
              </div>
              <div class="col-12 col-sm-6">
                <label for="last-name">Last Name</label>
                <input type="text" class="form-input" name="last-name" placeholder="Enter last name" />
              </div>
            </div>
    
            <div class="row">
              <div class="col-12 col-sm-6">
                <label for="email">Email</label>
                <input type="email" class="form-input" name="email" placeholder="Enter email" />
              </div>
              <div class="col-12 col-sm-6">
                <label for="github">GitHub</label>
                <input type="text" class="form-input" name="github" placeholder="Enter GitHub" />
              </div>
            </div>
            <fieldset class="group">
              <legend>Select standard pizza toppings</legend>
              <ul class="checkbox">
                <li>
                  <input type="checkbox" id="cb1" value="pepperoni" />
                  <label for="cb1">Pepperoni</label>
                </li>
                <li>
                  <input type="checkbox" id="cb2" value="sausage" />
                  <label for="cb2">Sausage</label>
                </li>
                <li>
                  <input type="checkbox" id="cb3" value="mushrooms" />
                  <label for="cb3">Mushrooms</label>
                </li>
                <li>
                  <input type="checkbox" id="cb4" value="onions" />
                  <label for="cb4">Onions</label>
                </li>
                <li>
                  <input type="checkbox" id="cb5" value="green peppers" />
                  <label for="cb5">Green Peppers</label>
                </li>
                <li>
                  <input type="checkbox" id="cb6" value="extra cheese" />
                  <label for="cb6">Extra Cheese</label>
                </li>
              </ul>
            </fieldset>
            <button class="btn btn-block btn-danger">Submit Form</button>
          </form>
        </div>
      </div>
    </div>
  </div>


  <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script type="text/javascript" src="./assets/js/script.js"></script>
</body>

</html>
```
{{% /tab %}}
{{% tab name="style.css" %}}
```css
input[type='checkbox'] {
  display: inline-block;
  margin-right: 0.25rem;
}

legend {
  font-weight: bold;
  margin-left: 20px;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: inline-block;
  padding: 0.5rem;
}

.group {
  margin-bottom: 1.25rem;
  margin-top: 1.25rem;
  padding: 0.125rem;
}

```
{{% /tab %}}

{{% tab name="index.js" %}}
```js
var formEl = $('#pizza-form');
var firstNameEl = $('input[name="first-name"]');
var lastNameEl = $('input[name="last-name"]');
var emailEl = $('input[name="email"]');
var githubEl = $('input[name="github"]');

function handleFormSubmit(event) {
  // Prevent the default behavior
  event.preventDefault();

  console.log('First Name:', firstNameEl.val());
  console.log('Last Name:', lastNameEl.val());
  console.log('Email:', emailEl.val());
  console.log('GitHub:', githubEl.val());

  // Select all checked options
  var checkedEl = $('input:checked');
  var selected = [];

  // Loop through checked options to store in array
  $.each(checkedEl, function () {
    selected.push($(this).val());
  });
  console.log('Toppings: ', selected.join(', '));

  // Clear input fields
  $('input[type="text"]').val('');
  $('input[type="email"]').val('');
  $('input[type="checkbox"]').prop('checked', false);
}

// Submit event on the form
formEl.on('submit', handleFormSubmit);

```
{{% /tab %}}
{{< /tabs >}}



