+++
title = "02. Arrays 👩‍🎓👨‍🎓"
weight = 2
tags = ["javascript"] 
+++

# 🏗 Log Welcome Messages to Console Using an Array

Implement the following user story:

* As an instructor, I want to create a list of student names and be able to add and rename names.

## Acceptance Criteria 

* It's done when the total number of elements in the array is logged to the console.  

* It's done when the message "Welcome to the class STUDENT_NAME" is logged using each element in the array. 

* It's done when the first element in the array is replaced with the name of a new student.

* It's done when, after an `if` statement confirms that the first element in the array has been replaced, the message "REPLACED_NAME is in class" is logged.

## 💡 Hints

What is the first index in an array: `0` or `1`? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* How could you use the array's `length` property to access the last element in an array of any length?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Creates an array containing names of five students in the class
var students = ["Sarah", "Orlando", "Heather", "Ismael", "Hung"];

// Logs length of the students array
console.log(students.length);

// Now, write a console log introducing each student
console.log("Welcome to the class " + students[0]);
console.log("Welcome to the class " + students[1]);
console.log("Welcome to the class " + students[2]);
console.log("Welcome to the class " + students[3]);
console.log("Welcome to the class " + students[4]);
   
// Replace the first student in the array with a new student Bob.
students[0] = "Bob";

// Use your Javascript to check if "Bob" is the first elemnt in the array 
if (students[0] === "Bob") {
    console.log(students[0] + " is in class!");
} 
```
{{% /expand%}}

