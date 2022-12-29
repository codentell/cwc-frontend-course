+++
title = "07. Iterative Methods 👩‍🏫🧑‍🏫"
weight = 7
tags = ["advanced javascript"] 
+++

```js
var numbers = [1, 2, 3, 4]

//Iterative Methods
numbers.forEach(lessThanThree)

function lessThanThree(i) {
  if (i < 3) {
    console.log(i.toString() + ' is less than 3');
  } else {
    console.log(i.toString() + ' is NOT less than 3');
  }
}

var numbersDoubled = numbers.map(multiply)

function multiply(i) {
 return i * 2
}

console.log(numbersDoubled)
```