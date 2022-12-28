+++
title = "10. Luxury Tax Calculator 👩‍🎓👨‍🎓"
weight = 10
tags = ["javascript"] 
+++


# Luxury Tax Calculator

* As a developer, I want to write an algorithm that will calculate how much luxury tax a hypothetical sports team will pay to sign three players.

## Instructions

* Create three variables that contain the salaries for each player (without the dollar sign or commas).
  
* Calculate and display the total salary for all three players.
  * If the team exceeded their spending limit, calculate and display the cost of the luxury tax.
  * The team's spending limit is $40,000,000.
  * The tax rate is 18%. Note that the 18% luxury tax is only paid on the the amount of salary OVER the team's spending limit. For example, if a team's payroll is $55,000,000, they only pay luxury tax on $15,000,000.

## 🏆 Bonus

If you have completed this activity,  further your knowledge by answering this question:

* How would you receive input from a user in the browser?
* How could you hold a list of players in one variable?

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Luxury Tax

var player1 = 20235406;
var player2 = 15000000;
var player3 = 25000000;
var tax;

var total = player1 + player2 + player3;

console.log('The total for all three players is: $' + total);

if (total > 40000000) {
  tax = (total - 40000000) * 0.18;
  console.log('Your team owes a luxury tax in the amount of: $' + tax);
} else {
  console.log('Your team owes no luxury tax');
}
```
{{% /expand%}}