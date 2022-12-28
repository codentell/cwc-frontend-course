+++
title = "07. Switch 👩‍🎓👨‍🎓"
weight = 7
tags = ["javascript"] 
+++

# 🏗️ Conditional Days of the Week

Implement the following user story:

* As a developer I want to compare the differences between if-statements and switch-case. I want to create an app where a user inputs a number between 1 and 7 and the app prints the day of the week associated with that number.

## Acceptance Criteria

* Build `if` statements to find the day of the week based on a number from 1 through 7.
  * Each statement should alert the user what day they picked
* Rebuild using switch-case

---




## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
var userInput = prompt('Please input a number between 1 and 7, inclusive: ');

var userDay = parseInt(userInput);

if (userDay === 1) {
    alert('You entered the number that equals: Monday');
} else if (userDay === 2) {
    alert('You entered the number that equals: Tuesday');
} else if (userDay === 3) {
    alert('You entered the number that equals: Wednesday');
} else if (userDay === 4) {
    alert('You entered the number that equals: Thursday');
} else if (userDay === 5) {
    alert('You entered the number that equals: Friday');
} else if (userDay === 6) {
    alert('You entered the number that equals: Saturday');
} else if (userDay === 7) {
    alert('You entered the number that equals: Sunday');
} else {
    alert('You entered an incorrect number!!!');
}

/*
switch (userDay) {
  case 1:
    alert("You entered the number that equals: Monday"); 
    break;
  case 2:
    alert("You entered the number that equals: Tuesday");
    break;
  case 3:
    alert("You entered the number that equals: Wednesday"); 
    break;
  case 4:
    alert("You entered the number that equals: Thursday"); 
    break;
  case 5:
    alert("You entered the number that equals: Friday"); 
    break;
  case 6:
    alert("You entered the number that equals: Saturday"); 
    break;
  case 7:
    alert("You entered the number that equals: Sunday"); 
    break;
  default:
    alert("You entered an incorrect number!!!"); 
}
*/
```

{{% /expand%}}