+++
title = "04. Organizing Tests  👩‍🏫🧑‍🏫"
weight = 4
tags = ["oop"] 
+++


### index.js 
```js
const TodoList = require("./todoList");

const todoList = new TodoList();

todoList.addTodo("Get Eggs");
todoList.addTodo("Get Milk");
todoList.addTodo("Get Bread");

console.log("Next todo:", todoList.getNextTodo());
todoList.completeNextTodo();

console.log("Next todo:", todoList.getNextTodo());
todoList.completeNextTodo();

console.log("Next todo:", todoList.getNextTodo());
todoList.completeNextTodo();
```

### todo.js

```js
function Todo(text) {
  if (typeof text !== "string" || !text.trim().length) {
    throw new Error("Expected parameter 'text' to be a non empty string");
  }

  this.text = text;
}

module.exports = Todo;
```
### todoList.js
```js
const Todo = require("./todo");

function TodoList() {
  this.todos = [];
}

TodoList.prototype.addTodo = function(text) {
  this.todos.push(new Todo(text));
};

TodoList.prototype.getNextTodo = function() {
  return this.todos[0];
};

TodoList.prototype.completeNextTodo = function() {
  return this.todos.shift();
};

module.exports = TodoList;
```