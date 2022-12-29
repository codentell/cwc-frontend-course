+++
title = "03. Functions 👩‍🎓👨‍🎓"
weight = 3
tags = ["advanced javascript"] 
+++

# 🏗️ Write Simple Functions

## Instructions

* Create Three Simple Functions
   
  * One function that adds 1 and 2 together using Function Declaration.
   
  * One function that subtracs 10 from 20 using Function Expression.
  
  * One function that calculates the area of a square using an outside variable, using either function declaration or expression. 


## 🏆 Bonus

If you have completed this activity, work through the following to further your knowledge:

* Do we always need to use `return`?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
function addOneAndTwo() {
  console.log(1+2);
  return
}

var subtractTwentyAndTen = function() {
  console.log(20-10);
  return
}

var side = 54;

function areaOfASquare() {
  var area = side * side;
  console.log('area: ', area)
  return
}

addOneAndTwo();
subtractTwentyAndTen();
areaOfASquare();
```

{{% /expand%}}