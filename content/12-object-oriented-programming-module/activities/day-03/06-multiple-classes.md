+++
title = "06. Multiple Classes 👩‍🎓👨‍🎓"
weight = 6
tags = ["oop"] 
+++

# Multiple Classes

In this activity, we will create a Store class that allows us to handle different interactions within the store. We will use multiple classes with differing purposes to practice the OOP paradigm.

## Instructions

* Since we will be using Jest in this activity, run `npm install` from your terminal. Remember that the command to run tests is `npm test`.

* Open [test/store.test.js](starter/test/store.test.js) and take a moment to familiarize yourself with the Store class tests.

* In the `store.js` file, create a `Store` class with the following properties:
  * Name
  * Stock
  * Revenue

* In `toy.js`, add the following properties:
  * Name
  * Price
  * Count

* In the `Store` class, create a method called `processProductSale` that takes in the product's name as a parameter. This method should increase the store's revenue by the price of the toy and decrease the toy's count by 1.

* If there's no more stock of a given toy, `console.log` a message and do not decrease the toy's `count` property.

* In the `Store` class, add a method called `replenishStock(name, count)` that increases the stock on a toy by the provided `count` parameter.

* `index.js` will be used to instantiate the objects. Uncomment lines as you add functionality.

### Hints

* It is recommended that you use these tests as guidance for this activity. Try working on each bit of functionality in conjuncture with its unit test, only moving on when the test passes.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### index.js
```js
const Store = require("./store");
const { toys } = require("./toy");

const store = new Store("Big Al's Toy Barn", toys);

store.welcome();
store.processProductSale("Action Figure");
store.processProductSale("Action Figure");
store.processProductSale("Rare Toy");
store.processProductSale("Action Figure");

store.processProductSale("Rare Toy");

store.replenishStock("Rare Toy", 2);
store.processProductSale("Rare Toy");

store.printRevenue();
```

### store.js
```js
class Store {
  constructor(name, stock) {
    this.name = name;
    this.stock = stock;
    this.revenue = 0;
  }

  processProductSale(name) {
    this.stock.forEach(item => {
      if (item.name === name) {
        if (item.count > 0) {
          item.count--;
          this.revenue += item.price;
          console.log(`Purchased ${item.name} for ${item.price}`);
        } else {
          console.log(`Sorry, ${item.name} is out of stock!`);
        }
      }
    });
  }

  replenishStock(name, count) {
    this.stock.forEach(item => {
      if (item.name === name) {
        item.count += count;
        console.log(`Replenished ${item.name} by ${item.count}`);
      }
    });
  }

  printRevenue() {
    console.log(`The revenue so far is ${this.revenue}`);
  }

  welcome() {
    console.log(`Welcome to ${this.name}!`);
  }
}

module.exports = Store;
```

### toy.js
```js
class Toy {
  constructor(name, price, count) {
    this.name = name;
    this.price = price;
    this.count = count;
  }
}

const toys = [
  new Toy("Action Figure", 14.99, 5),
  new Toy("Rare Toy", 17.99, 1)
];

module.exports = {
  Toy,
  toys
};
```

{{% /expand%}}