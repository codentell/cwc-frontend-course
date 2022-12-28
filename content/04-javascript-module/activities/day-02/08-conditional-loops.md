+++
title = "08. Conditional Loops 👩‍🎓👨‍🎓"
weight = 8
tags = ["javascript"] 
+++

# 🏗️ Conditional Days of the Week

Implement the following user story:

* As a developer I want to compare the differences between if-statements and switch-case. I want to create an app where a user inputs a number between 1 and 7 and the app prints the day of the week associated with that number.

## Acceptance Criteria

* Build `if` statements to find the day of the week based on a number from 1 through 7.
  * Each statement should alert the user what day they picked
* Rebuild using switch-case

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// This is our starting myFarm array.
var myFarm = ["chickens", "pigs", "cows", "horses", "ostriches"];

// Creating a variable to hold our array length.
var arrayLength = myFarm.length;

// Looping through our myFarm array.
for (var j = 0; j < arrayLength; j++) {

  // Console out the farm animal in the current index.
  console.log(myFarm[j]);

  // If the first character in the current animal is "c" or "o", alert the following message.
  if (myFarm[j].charAt(0) === "c" || myFarm[j].charAt(0) === "o") {
    alert("Starts with a c or an o!");
  }

}


```
{{% /expand%}}