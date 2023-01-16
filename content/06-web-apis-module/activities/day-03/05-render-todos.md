+++
title = "05. Render Todos 👩‍🎓👨‍🎓"
weight = 5
tags = ["web apis"] 
+++

# Render Todos

In this activity, you will be writing code to render an array of todo items to the list.

## Instructions

* Open the `script.js` file provided to you. You have been provided the necessary variable declarations as well as an array of todo items.

* Your goal is to create a function that will render our todos into a list in the browser.

  * Initially, set the text content of the `todoList` to an empty string.
  
  * `todoCountSpan` should show the total count of todos on the page.
  
* Inside of your `render` function, you will also need a `for` loop.

  * It should loop over the `todos` array, creating an `li` element for each index of the array.
  
  * It should set the content of the created `li` element to the value of the current array index.
  
  * Finally, the new `li` should be appended to the `ul` provided.

* Add an event listener so that, when a user hits `enter`, the value from the todo input field is pushed to our todo array.

* Make sure that empty values are not pushed to the array.

* Once the value has been added to the array, clear the input field and re-render the `todoList`.

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
    <title>Todo List</title>
  </head>
  <body>
    <div class="todos">
      <form id="todo-form" method="POST">
        <label for="todo-text">Add a Todo:</label>
        <input type="text" placeholder="What needs to be done?" name="todo-text" id="todo-text" />
      </form>
      <p>Todo Count: <span id="todo-count">0</span></p>
      <ul id="todo-list"></ul>
    </div>
    <script src="./script.js"></script>
  </body>
</html>
```

### script.js
```js
var todoInput = document.querySelector("#todo-text");
var todoForm = document.querySelector("#todo-form");
var todoList = document.querySelector("#todo-list");
var todoCountSpan = document.querySelector("#todo-count");

var todos = ["Learn HTML", "Learn CSS", "Learn JavaScript"];

renderTodos();

function renderTodos() {
  // Clear todoList element and update todoCountSpan
  todoList.innerHTML = "";
  todoCountSpan.textContent = todos.length;

  // Render a new li for each todo
  for (var i = 0; i < todos.length; i++) {
    var todo = todos[i];

    var li = document.createElement("li");
    li.textContent = todo;
    todoList.appendChild(li);
  }
}

// When form is submitted...
todoForm.addEventListener("submit", function(event) {
  event.preventDefault();

  var todoText = todoInput.value.trim();

  // Return from function early if submitted todoText is blank
  if (todoText === "") {
    return;
  }

  // Add new todoText to todos array, clear the input
  todos.push(todoText);
  todoInput.value = "";

  // Re-render the list
  renderTodos();
});
```
{{% /expand%}}