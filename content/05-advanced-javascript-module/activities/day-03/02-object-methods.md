+++
title = "02. Object Methods 👩‍🎓👨‍🎓"
weight = 2
tags = ["advanced javascript"] 
+++

# 🐛 Messages Not Logging to Console 

* Users should see a message log to the console indicating whether the shelter dog or cat is available.

## Expected Behavior

When a name is stored in the `chosenPet` variable, a message should log to the console indicating whether the pet is available and whether it is a dog or a cat. If the pet is not available, a message should indicate that and suggest the shelter's featured cat and dog. No errors should be returned. 

## Actual Behavior

No message is logged to the console, and an error message indicating an `Uncaught ReferenceError` is returned. 

## 💡 Hints

Look at each console log. What is the intended input? How can you use the object name and key to access the values and methods you need to make the code work?

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
var chosenPet = "Lulu";

var shelter = {
  dogs: ["Mackie", "Bernice", "Cookie Monster", "Spot"],
  cats: ["Astrid", "Lulu", "Fluffy", "Mouser"],
  apptMessage: function () {
    console.log("Email us at meetafriend@waywardpets.com to make an appointment to meet your new friend.");
  }
};

function dogMessage() {
  // ChosenPet is a variable that holds a value "Lulu"
  console.log("Congrats! " + chosenPet + ", a great dog, is available for adoption!");
  // The apptMessage method is a method on the shelter object
  shelter.apptMessage();
}

function catMessage() {
  console.log("Congrats! " + chosenPet + ", an awesome cat, is available for adoption!"); 
  // An object method needs a () to work! 
  shelter.apptMessage();
}

// To access the array you must use the object name and the key related to the array
if (shelter.dogs.includes(chosenPet)) {
  dogMessage();
} else if (shelter.cats.includes(chosenPet)) {
  catMessage();
} else {
  console.log("It looks like the pet is not available.");  
  // To access a value stored in the array, you use the object name, name of key and the value's index
  console.log("Check out our featured dog, " + shelter.dogs[0] + ", or our featured cat, " + shelter.cats[1]);
}
```
{{% /expand%}}




