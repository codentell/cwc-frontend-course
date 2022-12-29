+++
title = "08. Function Game 👩‍🎓👨‍🎓"
weight = 8
tags = ["advanced javascript"] 
+++

# Blackjack Game

In this mini-project you will work with a partner to complete a simple blackjack game.

## Instructions

* Create a simple blackjack game with the following properties:

  * Deals the player a random number between 4 and 21 inclusive.
  
    * If the player has 21 they win!
   
  * Deals a random number between 2 and 11 inclusive to the dealer.
   
  * If the player hits, add a number between 2 and 11.
   
    * If the player goes over 21 the lose.
     
    * If the player has 21, stay for them.
     
    * Repeat until they choose to stay or they bust
     
  * Once player stays add a number between 2 and 11 to the dealer's hand.
     
    * If dealer number is less than 17 add another number
     
    * Repeat until the number is over over 17 but less than 21, or if the dealer goes over 21
     
    * If dealer goes over 21 they lose.
  
  * Once dealer stops, and neither player bust, compare each number to 21. Whoever is closer wins!

* Pseudocode the outline of your game before you write any code.

* Create functions if you begin to repeat yourself.

### Notes

This is a difficult challenge. How you build this game is up to you. The goal here is to demonstrate when to use functions. If at any point you begin to type the same line of code, or if your code becomes unreadable, consider a function!

## Hints

  * Be sure that your random number generator is inclusive of the outer numbers.
   
  * We've used a lot of `for` loops. Don't forget that there are other types of loops.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
var game = {
    player: 0,
    dealer: 0,
    goal: 21,
    isPlayerTurn: false
};

function blackjack() {
    // Should give player a number between 4 and 21
    game.player = randomNum(4, 21);
    game.dealer = randomNum(2, 11);
    console.log('player', game.player);

    if (game.player === game.goal) {
        game.wins++;
        alert('Blackjack!');
    } else {
        do {
            gamePlay(game.player, game.dealer);
        } while (game.isPlayerTurn === true);
    }
}

// Function to hold the actual gameplay. Keeps the blackjack function clean
function gamePlay(playerTotal, dealerTotal) {
    // Should show the Dealer's number between 2 and 11
    // Player can Hit or Stay
    var hit = confirm(
        'Your hand is ' + playerTotal.toString() + '.\nThe Dealer shows ' + game.dealer.toString() + '. Hit or Stand?'
    );
    if (hit) {
        game.isPlayerTurn = true;

        // If Hit add a number between 2 and 11
        game.player = game.player + randomNum(2, 11);
        console.log('player', game.player);
        // If >21 Player loses
        if (game.player > game.goal) {
            gameEnd();
            alert('Player Bust with ' + game.player.toString());
        } else if (game.player === game.goal) {
            alert('You have 21!');
            dealerTurn();
        }
    } else {
        dealerTurn();
    }
}

// Function to Hold Dealer Turn. Keeps the gameplay function clean
function dealerTurn() {
    do {
        game.dealer = game.dealer + randomNum(2, 11);
        console.log('game.dealer', game.dealer);
        // If Stay show dealer number
        alert('Stand at ' + game.player.toString() + '.\nDealer shows ' + game.dealer);
        // if < 17 add number between 2 and 11, repeat if less than 17
    } while (game.dealer < 17);

    // if > 21 Dealer lose
    if (game.dealer > game.goal) {
        alert('Dealer Busts!');
        gameEnd();
    } else {
        // if neither lose, compare both numbers to 21. Whoever is closer wins.
        var dealerDistance = game.goal - game.dealer;
        var playerDistance = game.goal - game.player;

        if (playerDistance > dealerDistance) {
            alert('Dealer had ' + game.dealer.toString() + '.\nYou had ' + game.player.toString() + '.\nYou Lose :(');
            gameEnd();
        } else if (playerDistance < dealerDistance) {
            alert('Dealer had ' + game.dealer.toString() + '.\nYou had ' + game.player.toString() + '.\nYou Win :)');
            gameEnd();
        } else {
            alert('Dealer had ' + game.dealer.toString() + '.\nYou had ' + game.player.toString() + '.\n You Push.');
            gameEnd();
        }
    }
}

// Utility Function
function randomNum(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min + 1) + min);
}

function gameEnd() {
    game.isPlayerTurn = false;
}

var start = confirm('Would you like to play blackjack?');

if (start) {
    blackjack();
} else {
    alert('Come again!');
}
```

{{% /expand%}}