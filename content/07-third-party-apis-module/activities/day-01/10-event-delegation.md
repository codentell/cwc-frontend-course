+++
title = "10. Event Delegation 👩‍🎓👨‍🎓"
weight = 10
tags = ["third party apis"] 
+++


# 📖 Implement Shopping List Item Deletion

Implement the following user story:

* As an online shopper, I want to be able to remove items from my list.

## Acceptance Criteria

* It's done when each item's Remove button can be clicked to remove its respective shopping list item.

## 📝 Notes

Refer to the following documentation:

[jQuery documentation on event delegation](https://learn.jquery.com/events/event-delegation/)

## 💡 Hints

* Use your knowledge in DOM traversal to select an element's parent.

* The jQuery method for deleting an element is `.remove()`.

## 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge:

* What are some alternatives to using jQuery?.

You can read this [guide to whether you need jQuery](http://youmightnotneedjquery.com/) to see some alternatives.

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

function handleFormSubmit(event) {
  event.preventDefault();

  var shoppingItem = $('input[name="shopping-input"]').val();

  if (!shoppingItem) {
    console.log('No shopping item filled out in form!');
    return;
  }

  var shoppingListItemEl = $(
    '<li class="flex-row justify-space-between align-center p-2 bg-light text-dark">'
  );
  shoppingListItemEl.text(shoppingItem);

  // add delete button to remove shopping list item
  shoppingListItemEl.append(
    '<button class="btn btn-danger btn-small delete-item-btn">Remove</button>'
  );

  // print to the page
  shoppingListEl.append(shoppingListItemEl);

  // clear the form input element
  $('input[name="shopping-input"]').val('');
}

function handleRemoveItem(event) {
  // convert button we pressed (`event.target`) to a jQuery DOM object
  var btnClicked = $(event.target);

  // get the parent `<li>` element from the button we pressed and remove it
  btnClicked.parent('li').remove();
}

// use event delegation on the `shoppingListEl` to listen for click on any element with a class of `delete-item-btn`
shoppingListEl.on('click', '.delete-item-btn', handleRemoveItem);
shoppingFormEl.on('submit', handleFormSubmit);
```
{{% /expand%}}