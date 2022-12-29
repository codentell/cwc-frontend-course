+++
title = "04. Objects Methods 👩‍🎓👨‍🎓"
weight = 4
tags = ["advanced javascript"] 
+++

# 🏗️ Determine Total Cost of a Menu

Implement the following user story:

* As a coffee shop owner, I want to be able to see my entire menu, as well as calculate the total cost for the menu 

## Acceptance Criteria 

* It's done when the `menu` object has properties that store drink names, and prices. 

* It's done when an array of the drink names is printed to the console. 

* It's done when the total price of the menu is calculated and printed to the console.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Our Menu object
var menu = {
  coffee: 4.50,
  latte: 6.50,
  coldBrew: 6,
  matcha: 7
};

// We assign our menu values to the prices variable
var prices = Object.values(menu);

// Instantiate the total
var total = 0;

// We print the entire menu
console.log('The menu contains the following drinks:', Object.keys(menu));

// We loop through the values and add them to the total
for (let i = 0; i < prices.length; i++) {
  total += prices[i];
}

// We print the total cost
console.log('Total Menu Cost = $' + total);
```

{{% /expand%}}