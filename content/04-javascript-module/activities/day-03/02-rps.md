+++
title = "02. Rock Paper Scissors 👩‍🎓👨‍🎓"
weight = 2
tags = ["javascript"] 
+++

# Rock, Paper, Scissors

In this activity, you will work with a partner to build a rock-paper-scissors game using only JavaScript.

**Rules for rock-paper-scissors**

* Rock: wins against scissors, loses to paper, and ties against itself.
* Paper: wins against rock, loses to scissors, and ties against itself.
* Scissors: wins against paper, loses to rock, and ties against itself.

![RPS-Example-Picture](../images/RPS-example.png)

### Instructions

* Begin the process of coding out the rock-paper-scissors game.

* As a user:
  * I want to play Rock, Paper, Scissors against an automated opponent.
  * I can enter R, P, or S to signify my choice of rock, paper, or scissors.
  * I expect the computer to choose R, P, or S in return.
  * I want the option to play again whether I win or lose.
  * I want to see my total wins, ties, and losses after 10 rounds.

* The computer's selection must be random to ensure a fair game.

* Follow your pseudocode as much as you can, and if you get stuck don't worry, this is a challenging assignment.

## 💡 Notes

Refer to the documentation:

* [MDN Web Docs on Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```javascript
// Creates an array that lists out all of the options (Rock, Paper, or Scissors).
var computerChoices = [ 'r', 'p', 's' ];

// Creating variables to hold the number of wins, losses, and ties. They start at 0.
var wins = 0;
var losses = 0;
var ties = 0;

for (var i = 0; i < 10; i++) {
    // Randomly chooses a choice from the options array. This is the Computer's guess.
    var computerGuess = computerChoices[Math.floor(Math.random() * computerChoices.length)];

    // Collect the user's response and convert to lower case.
    var userGuess = prompt('Enter r, p, or s to play!');
    userGuess = userGuess.toLowerCase();

    // Only run game logic if user chose a valid option
    if (userGuess === 'r' || userGuess === 'p' || userGuess === 's') {
        alert('The computer chose ' + computerGuess);

        // Win/lose conditions:
        if (userGuess === computerGuess) {
            ties++;
            alert("You've tied " + ties + ' time(s).');
        } else if (
            (userGuess === 'r' && computerGuess === 's') ||
            (userGuess === 's' && computerGuess === 'p') ||
            (userGuess === 'p' && computerGuess === 'r')
        ) {
            wins++;
            alert("You've won " + wins + ' time(s)!');
        } else {
            losses++;
            alert("You've lost " + losses + ' time(s).');
        }
    }
}

// When the game is over, alert the totals to the user. We can use the \n character to make a line break.
alert('Total wins: ' + wins + '\nTotal ties: ' + ties + '\nTotal losses: ' + losses);
```
{{% /expand%}}


