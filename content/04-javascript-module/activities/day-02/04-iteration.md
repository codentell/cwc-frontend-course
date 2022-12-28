+++
title = "04. Iteration 👩‍🎓👨‍🎓"
weight = 4
tags = ["javascript"] 
+++

# 🏗️ Iterate Over an Array to Log Messages to Console

Implement the following user story:

* As a member of the class, I want to store a list of my classmates and use that list to create a greeting for each student on the list. 

## Acceptance Criteria

* It's done when the names of five classmates are stored in a single variable named `students`.

* It's done when the total number of elements in the `students` array is logged to the console. 

* It's done when, using a `for` loop, the greeting "Great to see you, CLASSMATE_NAME!" logs to the console for each classmate's name in the `students` array. 

## 💡 Hints

How can you access each element using the element's index and the array name? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* What’s a `while` loop?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Creates an array containing names of five student in the class
  var students = ["Sarah", "Orlando", "Heather", "Ismael", "Hung"];

  // Logs length of the array
  console.log(students.length);

  // For loop starts at 0, runs while i is less than length of student array
  // Increments by 1
  for(var i=0; i < students.length; i++) {
    // This statement will run each time the loop is executed
    console.log("Great to see you, " + students[i] + "!");
  }
```
{{% /expand%}}