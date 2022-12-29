+++
title = "02. Objects "
weight = 2
tags = ["advanced javascript"] 
+++

# 🏗️ Log Customer's Drink Order Using an Object

Implement the following user story:

* As a coffee shop owner, I want to store data about my customer's drink order in an object and log a message indicating whether the drink is ready or still in the queue.

## Acceptance Criteria

* It's done when the `customerOrder` object has three properties that store the drink's name, the number of sugars, and a Boolean indicating whether the order is ready.

* It's done when the drink name and the number of sugars is logged to the console.

* It's done when, if the order is ready, the message `"Ready for pick-up"` logs.

* It's done when, if the order is not ready, the message `"Still in order queue"` logs.

## 💡 Hints

How can we use dot notation or bracket notation to access an object's values?

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* What is a `for...in` statement? How can you use it to iterate over an object’s properties?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Object customerDrink with three properties
var customerDrink = {
  name: "coffee",
  sugars: 3,
  isReady: true
};

// This logs the entire object
console.log(customerDrink);

// Note that in dot notation, the name of the object is followed by the key
if (customerDrink.isReady) {
  console.log("Ready for pick-up: " + customerDrink.name + " with " + customerDrink.sugars + " sugars.");

// Note that in bracket notation, the key is inside brackets and surrounded by quotes
} else {
  console.log("Still in order queue: " + customerDrink["name"] + " with " + customerDrink["sugars"] + " sugars.");
}

```

{{% /expand%}}