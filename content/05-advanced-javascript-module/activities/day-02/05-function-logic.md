+++
title = "05. Function Logic 👩‍🎓👨‍🎓"
weight = 5
tags = ["advanced javascript"] 
+++

# 🏗️ Write Function to Evaluate Equality of Two Values

Work with a partner to implement the following user story:

* As a developer, I want to know when two values are equal to one another.

## Acceptance Criteria

* Create a function using function declaration that checks if two parameters are equal in both value and type, just value, or not equal in any way and prints it to the console.

  * Call the function so that it prints each option.

* Create a function using function expression that iterates through an array and checks if each index is less than 10 and prints if it is or isn't.

  * Call the function.

## 💡 Hints

How can we use parameters to give a name to the two values that we want to evaluate with the function? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What is hoisting?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// isEqual using function declaration
function isEqual(x, y) {
  if (x === y) {
    console.log('They are equal in type and value');
  } else if (x == y) {
    console.log('They are equal in value');
  } else {
    console.log('They are not equal');
  }
  return;
}

// Logs "They are equal in type and value"
isEqual(10, 10);

// Logs "They are equal in value"
isEqual('10', 10);

// Logs "They are not equal"
isEqual(10, true);

var numbers = [1, 3, 5, 7, 9, 11]

// Function expression
var lessThanTen = function(arr) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] < 10) {
      //We used the .toString() method so that we could print cleanly.
      console.log(arr[i].toString() + ' is less than 10')
    } else {
      console.log(arr[i].toString() + ' is NOT less than 10')
    }
  }
}

lessThanTen(numbers);
```
{{% /expand%}}