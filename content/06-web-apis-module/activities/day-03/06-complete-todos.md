+++
title = "06. Complete Todos 👩‍🎓👨‍🎓"
weight = 6
tags = ["web apis"] 
+++

# Complete Todos

In this activity, we will create a "Complete" button that successfully removes a todo item from the list when clicked.

Then we will work on storing our todos in `localStorage`

## Instructions

1. Create a "Complete" Button

* Modify your `renderTodos()` function:

  * When a new todo is created, add a `data-index` for each `li`.

  * Generate a button that says "Complete" and append it to your `li`.

* Add an event listener so that, when a user clicks the `complete` button, it accesses the `data-index` value and removes that todo element from the list.

**Hint:** You can use `setAttribute` for `data-index` and `splice` to remove your todo from the list.

2. Store todos in `localStorage`

* Inside the `init()` function:

  * Set a variable called `storedTodos` that retrieves the todos from `localStorage` and parses the JSON string to an object.

  * Check if the todos were retrieved from `localStorage` and, if so, set a `todos` variable with the `storedTodos`.

  * Lastly, render the todos to the DOM.

* Inside the `storeTodos()` function:

  * Stringify and set the "todos" key in `localStorage` to the `todos` array.

**Hint:** You will need to use `JSON.stringify` and `JSON.parse`.

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

var todos = [];

init();

function renderTodos() {
  // Clear todoList element and update todoCountSpan
  todoList.innerHTML = "";
  todoCountSpan.textContent = todos.length;

  // Render a new li for each todo
  for (var i = 0; i < todos.length; i++) {
    var todo = todos[i];

    var li = document.createElement("li");
    li.textContent = todo;
    li.setAttribute("data-index", i);

    var button = document.createElement("button");
    button.textContent = "Complete";

    li.appendChild(button);
    todoList.appendChild(li);
  }
}

function init() {
  // Get stored todos from localStorage
  // Parsing the JSON string to an object
  var storedTodos = JSON.parse(localStorage.getItem("todos"));

  // If todos were retrieved from localStorage, update the todos array to it
  if (storedTodos !== null) {
    todos = storedTodos;
  }

  // Render todos to the DOM
  renderTodos();
}

function storeTodos() {
  // Stringify and set "todos" key in localStorage to todos array
  localStorage.setItem("todos", JSON.stringify(todos));
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

  // Store updated todos in localStorage, re-render the list
  storeTodos();
  renderTodos();
});

// When a element inside of the todoList is clicked...
todoList.addEventListener("click", function(event) {
  var element = event.target;

  // If that element is a button...
  if (element.matches("button") === true) {
    // Get its data-index value and remove the todo element from the list
    var index = element.parentElement.getAttribute("data-index");
    todos.splice(index, 1);

    // Store updated todos in localStorage, re-render the list
    storeTodos();
    renderTodos();
  }
});
```

### style.css
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  font-family: "Concert One", cursive;
  font-size: 16px;
}

input {
  height: 50px;
  width: 100%;
  padding: 6px;
  margin-top: 10px;
  font-size: 2.4em;
  border: none;
}

ul {
  list-style-type: none;
  padding: 0;
  background-color: white;
}

li {
  height: 50px;
  margin-top: 5px;
  margin-bottom: 5px;
  padding: 5px;
  background-color: #ff5d88;
  color: white;
  font-size: 1.5em;
  line-height: 1.5;
}

li:before {
  content: "\200B";
  position: absolute;
}

li::after {
  content: " ";
  display: block;
  clear: both;
}

li button {
  float: right;
  border: none;
  height: 40px;
  cursor: pointer;
  background-color: #ff9500;
  color: white;
  font-size: 1em;
}

li button:hover {
  background-color: #febc5d;
}

.todos {
  width: 800px;
  margin: 0 auto;
  margin-top: 40px;
}
```


{{% /expand%}}