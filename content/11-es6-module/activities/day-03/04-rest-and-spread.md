+++
title = "04. 👩‍🎓👨‍🎓"
weight = 4
tags = ["es6"] 
+++

# 📐 Add Comments to Implementation and Use of Rest and Spread Operators

Work with a partner to add comments describing the functionality of the code found in [index.js](./starter/index.js).

## 📝 Notes

Refer to the documentation: 

* [MDN Web Docs on spread](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

* [MDN Web Docs on rest](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)

* [MDN Web Docs on reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

---

## 🏆 BONUS

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* On what other data types can you use the spread operator or rest parameters?

Use [Google](https://www.google.com) or another search engine to research this.

---
## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.js
```js
// Exercise 1
const songs = ['Creep', 'Everlong', 'Bulls On Parade', 'Song 2', 'What I Got'];

// Which operator is being used here?
// We are using the spread operator to copy the 'songs' array into another array
const newSongs = [...songs];

// What do you expect to be logged in the console?
// ["Creep", "Everlong", "Bulls On Parade", "Song 2", "What I Got"];
console.log(newSongs);

// Exercise 2
const addition = (x, y, z) => {
  const array = [x, y, z];
  // What does the reduce() method do?
  // The reduce() method executes the reducer function on each element of the array
  return array.reduce((a, b) => a + b, 0);
};
// What do you expect to be logged in the console?
// 6
console.log(addition(1, 2, 3));

// What is this syntax that is being used as the parameter?
// We are using the rest parameter syntax that allows us to represent an indefinite number of arguments as an array
const additionSpread = (...array) => {
  return array.reduce((a, b) => a + b, 0);
};

// What do you expect to be logged in the console?
// 6
console.log(additionSpread(1, 2, 3));

// What do you expect to be logged in the console?
// 110
console.log(additionSpread(1, 2, 3, 4, 100));
```
{{% /expand%}}