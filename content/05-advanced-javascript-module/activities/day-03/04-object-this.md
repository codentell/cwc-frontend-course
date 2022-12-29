+++
title = "04. Object this 👩‍🎓👨‍🎓"
weight = 4
tags = ["advanced javascript"] 
+++

# 📐 Add Comments to Implementation of this

Add comments describing the functionality of the code found in [starter folder](./starter/script.js).

## Notes

Refer to the documentation:

[MDN Web Docs on this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* JavaScript has its own built-in `Math` object with mathematical functions we can use. How can we combine `Math.floor()` and `Math.random()` to randomly select an element from an array? 

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// This refers to the window
console.log(this);

// This refers to the window object
function helloThis() { 
   console.log("Inside this function, this is " + this); 
   }

// This refers to the child object. Will console log 20
var child = { 
   age: 10,
   ageTenYears: function() {
       console.log(this.age + 10); 
   }
};

// This refers to the investment object. Will log 5750
var investor = {  
  name: "Cash Saver",
  investment: {
    initialInvestment: 5000,
    investmentGrowth: function() {
      console.log(this.initialInvestment * 1.15)
    }
   }   
};

// Call the function helloThis to check results
helloThis();

// Call the object methods to check results
child.ageTenYears();
investor.investment.investmentGrowth();
```
{{% /expand%}}