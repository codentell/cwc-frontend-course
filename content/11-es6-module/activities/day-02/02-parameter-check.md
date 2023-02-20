+++
title = "02. Parameter Check 👩‍🎓👨‍🎓"
weight = 2
tags = ["es6"] 
+++

# 🏗️ Implement `process.argv`

Work with a partner to implement the following user story:

* As a developer, I want to use command-line arguments as input when writing Node.js applications.

## Acceptance Criteria

* It's done when I have created a file, `index.js`, in the working directory.

* It's done when I use `process.argv` to assign two arguments to variables.

* It's done when I compare those two variables to see whether they are the same or not.

* It's done if the program returns `true` when the values are the same and `false` if they are not. 

## 💡 Hint

How many different ways can you solve this problem? Remember that there is not just one correct solution.

## 🏆 BONUS

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What is the difference between `===` and `==` when comparing two values in JavaScript?

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```js
const a = process.argv[2];
const b = process.argv[3];

// Using a conditional statement
if (a === b) {
  console.log(true);
} else {
  console.log(false);
}

// Using a ternary operator
console.log(a === b ? true : false)

// Comparing variables
console.log(a === b);

// Comparing argument values directly
console.log(process.argv[2] === process.argv[3]);
```
{{% /expand%}}