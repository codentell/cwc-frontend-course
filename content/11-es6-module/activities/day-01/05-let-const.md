+++
title = "05. Let Const 👩‍🏫🧑‍🏫"
weight = 6
tags = ["es6"] 
+++

### let
```js
// 1. When using var, our counter exists after a for-loop is done

for (var i = 0; i < 5; i++) {
  console.log(i);
}

console.log(i); // Prints 5

// When using let, our counter is not defined outside of the for-loop block

let x = 42;

for (let j = 0; j < 5; j++) {
  console.log(j);
  console.log(x);
}

console.log(j); // ReferenceError: j is not defined

let j = 42;
console.log(j); // prints 42

// ==========================================================================

// 2. When using while loops, any values we create inside exist outside of the while-loop block

// var count = 0;

// while (count < 5) {
//   var tripled = count * 3;
//   count++;
// }

// console.log(tripled); // Prints 12

// ==========================================================================

// 3. When using let, values defined inside of the while-loop block don't exist outside of it

// let c = 0;

// while (c < 5) {
//   let quadrupled = c * 3;
//   c++;
// }

// console.log(quadrupled); // ReferenceError: quadrupled is not defined

// ==========================================================================

// 4. When writing conditionals, values defined inside the conditional block exist outside of it

// if (true) {
//   var favoriteColor = "red";
// }

// console.log(favoriteColor); // Prints `red`

// When using let, values defined inside of a conditional block don't exist outside

// let favoriteFood;

// if (true) {
//   favoriteFood = "pizza";
// }

// This works since favoriteColor is not defined inside of a block
// console.log(favoriteFood);
// Prints `pizza`
```

### const
```js
// 1. const can be used for values which we will not reassign

const age = 25;

age++; // TypeError: Assignment to constant variable.

// ==========================================================================

// const name = "";

// name = "Cherie"; // TypeError: Assignment to constant variable.

// ==========================================================================

// 2. const doesn't mean `constant value`, instead means `constant reference`

// Unlike primitive data types, objects and arrays are passed by reference, rather than passed by value
// const beatles = ["John", "Paul", "Ringo"];
// beatles.push("George");

// This works because by updating an array's contents, we aren't changing the reference to the underlying array
// console.log(beatles); // Prints `["John", "Paul", "Ringo", "George"]`

// console.log(beatles);

// const person = { name: "Brianna", age: 11 };
// person.age++;
// person.favoriteMovie = "Spider-Man";
// person.name = "Carla";

// console.log(person); // Prints `{ name: 'Carla', age: 12, favoriteMovie: 'Spider-Man' }`

// ==========================================================================

// 3. While we can MODIFY arrays and objects that are using `const`, we can't reassign them

// const item = {
//   id: 23,
//   title: "Underwater Basket-Weaving DVD",
//   price: "$17.99"
// };

// item.price = "$1.99";

// console.log(item);

// item = {
//   id: 11,
//   title: "Underwater Basket-Weaving Shoes",
//   price: "$101.43"
// }; // TypeError: Assignment to constant variable.

// const ninjaTurtles = [];

// The same rules apply to arrays, we can MODIFY them, but not completely reassign them

// ninjaTurtles = [
//   "Michaelangelo",
//   "Leonardo",
//   "Raphael",
//   "Donatello"
// ]; // TypeError: Assignment to constant variable.


```