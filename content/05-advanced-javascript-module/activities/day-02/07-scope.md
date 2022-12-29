+++
title = "07. Scope 👩‍🎓👨‍🎓"
weight = 7
tags = ["advanced javascript"] 
+++

# 🐛 Messages Not Logging to Console Due to Undefined Variables

Work with a partner to resolve the following issue(s):

* As a developer, I want to log messages to the console using variables declared in both global and local scope. 

## Expected Behavior

When the console is opened, a series of messages should log to the console. 

## Actual Behavior

When the console is opened, an error message indicates that at least one variable is undefined, and messages do not log.

## 💡 Hints

Think about how the variable is being used. Is it being made available to all functions, or is it only being used by one function? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What are lexical and block scope?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Shout is declared in the global scope and is available to both functions 
var shout = "Shout";

function justShout() {
  console.log(shout + ", " + shout);
  return;
 }
 
function shoutItAllOut() {
  console.log(shout + " it all out! ");
  return;
 }
 
justShout();
shoutItAllOut();
 
// Lions is declared locally so it is available only to the sayLions function
function sayLions() {
  var animal = "Lions"; 
  console.log(animal);
  return;
}
 
// Tigers is declared locally so it only available to the sayTigers function 
function sayTigers() {
  var animal = "Tigers";
  console.log("and " + animal + " and "); 
  return;
 }
 
// Variables of the same name should not be declared in global and local scope
// Kept global scope
var bears = "Bears";
 
// Removed local scope
function sayBears() {
  console.log(bears + "! OH  MY!");
  return;
 }

sayLions();
sayTigers();
sayBears();
 
// Declaring sing in the outer function makes it available to the inner and outer function
function singAlong() {
  var sing = "Sing";
  console.log(sing + ",");
  var singASong = function () {  
    console.log(sing + " a Song.");
   };
  singASong();
 }
 
singAlong();
 
```

{{% /expand%}}

