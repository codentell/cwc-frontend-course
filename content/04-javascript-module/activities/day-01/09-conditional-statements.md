+++
title = "09. Conditional Statements 👩‍🎓👨‍🎓"
weight = 9
tags = ["javascript"] 
+++

# 🏗️ Create an Algorithm Using Conditional Statements

* As a developer, I want to write an algorithm that will take in two expressions and evaluate whether both expressions evaluate to `true`, only one expression evaluates to `true`, or both expressions evaluate to `false`.

## Acceptance Criteria

* It's done when the message "True ✅ True ✅" is logged when both `expression1` and `expression2` are true.

* It's done when the message "True ✅ False ❌" is logged when `expression1` is true. 

* It's done when the message "False ❌ True ✅" is logged when `expression2` is true. 

* It's done when the message "False ❌ False ❌" is logged when both `expression1` and `expression2` are false. 

## 💡 Hints

Before you start writing your algorithm, do you have a plan documented in plain language that describes how you will use JavaScript to get it done?

## 🏆 Bonus

If you have completed this activity, further your knowledge by answering this question:

* What is a switch case? 

Use [Google](https://www.google.com) or another search engine to research this.

---

## starter code 
```js
// Change the values and operators below to test your algorithm meets all conditions
var x = 50;
var expression1 = (x < 25);
var expression2 = (x > 50);

// Write Your JavaScript Code Here
//...
```

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Change the values and operators below to test your algorithm meets all conditions
var x = 50;
var expression1 = (x < 25);
var expression2 = (x > 50);

// Write Your JavaScript Code Here
// Check if both expressions are true using &&

if(expression1 && expression2) {
    console.log("True ✅ True ✅");

// If both conditions are not true, check if expression1 is true
} else if (expression1) {
    console.log("True ✅ False ❌");

// If expression1 is not true, then check if expression2 is true
} else if (expression2) {
    console.log("False ❌ True ✅");

// If none of the conditions above evaluate to true, both expressions must be false
} else {
    console.log("False ❌ False ❌");
}
```
{{% /expand%}}
