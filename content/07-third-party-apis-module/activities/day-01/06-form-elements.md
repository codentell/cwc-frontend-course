+++
title = "06. Form Elements 👩‍🎓👨‍🎓"
weight = 6
tags = ["third party apis"] 
+++

# 📖 Implement a Shopping List Form

Implement the following user storys:

* As an online shopper, I want to be able to add items to my shopping list so that I can view them all in one place.

* As an online shopper, I want to be able to quickly add another item to my list.

## Acceptance Criteria

* It's done when the form can be submitted and the value in the input field is captured and printed to the page as a list item.

* It's done when the form's input field is cleared upon a successful submission.

## 📝 Notes

Refer to the following documentation:

[jQuery documentation on forms](https://api.jquery.com/category/forms/)

## Assets

The following image demonstrates the web application's appearance and functionality:

![A shopping list app shows an input field with a button to Add Item, above a shopping list.](../images/06-solution-screenshot.png)

---

## 💡 Hints

* Prevent the default behavior of the `submit()` event.

* What jQuery form method can you use to retrieve the input field's data?

## 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge:

* How can we reset form elements using plain JavaScript?

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
  <title>jQuery Shopping List</title>
  <link rel="stylesheet" type="text/css" href="./assets/css/jass.css" />
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css" />
</head>

<body class="bg-dark text-light">
  <main class="my-5 mx-auto">
    <h1>Shopping List</h1>
    <hr />

    <h2>Add an item to the list.</h2>
    <form id="shopping-form">
      <input type="text" class="form-input w-100" id="shopping-input" name="shopping-input" placeholder="Enter item name" />
      <button class="btn btn-info">Add Item</button>
    </form>

    <ul id="shopping-list"></ul>
  </main>

  <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>

  <!-- Your JavaScript file -->
  <script type="text/javascript" src="assets/js/script.js">
  </script>
</body>

</html>
```

### index.js
```js
var shoppingFormEl = $('#shopping-form');
var shoppingListEl = $('#shopping-list');

// create function to handle form submission
function handleFormSubmit(event) {
  event.preventDefault();

  // select form element by its `name` attribute and get its value
  var shoppingItem = $('input[name="shopping-input"]').val();

  // if there's nothing in the form entered, don't print to the page
  if (!shoppingItem) {
    console.log('No shopping item filled out in form!');
    return;
  }

  // print to the page
  shoppingListEl.append('<li>' + shoppingItem + '</li>');

  // clear the form input element
  $('input[name="shopping-input"]').val('');
}

// Create a submit event listener on the form element
shoppingFormEl.on('submit', handleFormSubmit);
```
{{% /expand%}}