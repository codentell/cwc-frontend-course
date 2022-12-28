+++
title = "03. Console Variables 👩‍🎓👨‍🎓"
weight = 3
tags = ["javascript"] 
+++

# 🏗️ Link External JavaScript File andLog Introduction Messages to Console Using Values Stored in Variables 

* As a developer, I want to link an external JavaScript file to an existing `index.html` file to add JavaScript functionality to my static webpage. I also want to input data about my name, the number of pets I own, and a fun fact about myself and log that introduction to the console.

## Acceptance Criteria

* It's done when I open the `index.html` file, navigate to the console, and see the message contained in the `script.js` file logged to the console. 
  
* It's done when I store a name in a variable called `personName` and this line is logged to the console: "My name is `VALUE_STORED_IN_VARIABLE_NAME`."

* It's done when I store a number in a variable called `pets` and this line is logged to the console: "I have `VALUE_STORED_IN_VARIABLE_PETS` pet(s)."

* It's done when I store a fun fact in a variable called `funFact` and this line is logged to the console: "Fun fact: `VALUE_STORED_IN_VARIABLE_FUNFACT`."

## 💡 Hints

How can we combine values using the concatenation operator (`+`) to log a single message to the console?

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* What happens when you concatenate two variables in a single console log using `+`? Is the result what you expected? Why or why not? 

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### script.js
```javascript
// Declare variables using var
var personName = 'Sakura';
var pets = 3;
var funFact = 'I like pineapple on my pizza.';

// Use + to combine data and variable names in a single console log
console.log('My name is ' + personName + '.');
console.log('I have ' + pets + ' pet(s).');
console.log('Fun fact: ' + funFact);

// When re-assigning variables, use variable name
personName = 'Mateo';
pets = 5;
funFact = 'I was a yo-yo champ in third grade.';

// Logs message with re-assigned values
console.log('My name is ' + personName + '.');
console.log('I have ' + pets + ' pet(s).');
console.log('Fun fact: ' + funFact);
```

{{% /expand%}}