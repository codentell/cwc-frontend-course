+++
title = "06. Maths 👩‍🎓👨‍🎓"
weight = 6
tags = ["es6"] 
+++

# 🐛 Implement Modules

Work with a partner to resolve the following issue(s):

* Users should be able to import and use the `maths.js` module to execute simple math operations.

## Expected Behavior

* When I run `node index.js sum 3 4` in the command line, it should print out `7`.

* When I run `node index.js difference 3 4` in the command line, it should print out `-1`.

* When I run `node index.js product 3 4` in the command line, it should print out `12`.

* When I run `node index.js quotient 3 4` in the command line, it should print out `0.75`.

## Actual Behavior

* Nothing happens when I run the commands because the `index.js` file is empty.

## Steps to Reproduce the Problem

1. Navigate to the `Unsolved` folder in the command line.

2. Run `node index.js sum 3 4` in the command line.

## Instructions

Follow the prompts in the `index.js` file to complete the expected behaviour.

## 💡 Hint

What will the `parseInt()` method allow us to do?

## 🏆 BONUS

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* How can you export functions and objects directly?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### math.js

```js
module.exports = {
  sum: (a, b) => a + b,
  difference: (a, b) => a - b,
  product: (a, b) => a * b,
  quotient: (a, b) => a / b,
};
```

### index.js
```js
const maths = require('./maths');

const operation = process.argv[2];

const numOne = parseInt(process.argv[3]);
const numTwo = parseInt(process.argv[4]);

switch (operation) {
  case 'sum':
    console.log(maths.sum(numOne, numTwo));
    break;
  case 'difference':
    console.log(maths.difference(numOne, numTwo));
    break;
  case 'product':
    console.log(maths.product(numOne, numTwo));
    break;
  case 'quotient':
    console.log(maths.quotient(numOne, numTwo));
    break;
  default:
    console.log('Check your maths!');
}
```
{{% /expand%}}
