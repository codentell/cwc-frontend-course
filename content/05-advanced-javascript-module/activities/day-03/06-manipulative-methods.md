+++
title = "06. Manipulative methods 👩‍🎓👨‍🎓"
weight = 6
tags = ["advanced javascript"] 
+++

# 📖 Implement Array and String Manipulative Methods

Work with a partner to implement the following user stories:

* As a developer, I want to use array methods to add and remove elements from an array and join two arrays.

* As a developer, I want to use a string method to return a new string that contains only capital letters. 

## Acceptance Criteria

* It's done when the string `"Canis Major"` is added as the first element of the `constellations` array and no elements are removed. 

* It's done when `"Venus"` is removed from the `planets` array.

* It's done when the arrays `constellations` and `planets` are joined to form a new array named `galaxy`. The arrays `constellations` and `planets` should not be altered.

* It's done when the string `"polaris"` is converted into all capital letters and the new string is stored in a variable.

## 📝 Notes

Refer to the documentation:

[MDN Web Docs on array instance methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Instance_methods)

[MDN Web Docs on string instance methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Instance_methods)

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What happens when you use `typeof` on an array? What is returned? Is that what you expected? Why or why not? 

Use [Google](https://www.google.com) or another search engine to research this. 

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
var constellations = ["Orion", "Scorpius", "Lyra", "Ursa Major", "Ursa Minor"];
var planets = ["Earth", "Saturn", "Mars", "Jupiter", "Uranus", "Venus"];
var star = "polaris";

// The unshift method adds an element to the beginning of the array 
constellations.unshift("Canis Major");
console.log(constellations);

// The pop method removes the last element in the array
planets.pop();
// The original array is changed
console.log(planets);

//The concat method joins constellations and planets array and returns new array
var galaxy = constellations.concat(planets);
//The galaxy and planet arrays are unchanged
console.log(planets);
console.log(constellations);
console.log(galaxy);

// The toUpperCase method makes all the letters in the string "polaris" capital letters
var upperCaseStar = star.toUpperCase();
console.log(upperCaseStar);
// The original string is unchanged
console.log(star);
```
{{% /expand%}}