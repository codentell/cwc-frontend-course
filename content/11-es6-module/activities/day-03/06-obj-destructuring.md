+++
title = "06. Obj Destructuring 👩‍🎓👨‍🎓"
weight = 6
tags = ["es6"] 
+++

# 📖 Implement and Recognize Object Destructuring

Implement the following user story:

* As a developer, I want to be able to pull out data from objects and arrays into variables.

## Acceptance Criteria

* It's done when I have destructured the objects to pull out the data that are logged in the console.

* It's done when I have destructured the array to pull out the data that are logged in the console.

* It's done when I have run `node index.js` after destructuring to confirm the values logged in the console.

## 📝 Notes

Refer to the documentation: 

[MDN Web Docs on object destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

---

## 🏆 BONUS

If you have completed this activity, work through the following challenge to further your knowledge:

* How can we take a property from an object and assign it to a variable with a different name when we are destructuring it?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```js
// 1. Object
const nodejs = {
  name: 'Node.js',
  type: 'JavaScript runtime environment',
};

const { name, type } = nodejs;

console.log(name); // <= Node.js
console.log(type); // <= JavaScript runtime environment

// 2. Nested Object
const js = {
  name: 'JavaScript',
  type: 'programming language',
  version: 'ES6',
  tools: {
    frameworks: {
      framework1: 'AngularJS',
      framework2: 'Vue.js',
    },
    libraries: {
      library1: 'jQuery',
      library2: 'React',
    },
  },
};

const { framework1, framework2 } = js.tools.frameworks;

console.log(framework1); // <= AngularJS
console.log(framework2); // <= Vue.js

// 3. Arrays
const languages = ['HTML', 'CSS', 'JavaScript'];

const [markup, style, scripting] = languages;

console.log(markup, style, scripting); // <= HTML CSS JavaScript
console.log(markup); // <= HTML

```
{{% /expand%}}