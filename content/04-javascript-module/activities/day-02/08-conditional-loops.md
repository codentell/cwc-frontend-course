+++
title = "08. Conditional Loops 👩‍🎓👨‍🎓"
weight = 8
tags = ["javascript"] 
+++

# 🏗️ Conditional Loops

Implement the following user story:

* As a developer I want an app that will print an array of animals, but will also alert the user if any of the animal names begin with a "c" or an "o"

## Acceptance Criteria

* Loop through the following array and log the name of each animal:

  `var myFarm = ["chickens", "pigs", "cows", "horses", "ostriches"];`

* Alert the user if the first letter of an animal's name begins with a "c" or an "o"

## 💡 Hints

How can you access the first character of a string?


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