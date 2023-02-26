+++
title = "02. Classes 👩‍🎓👨‍🎓"
weight = 2
tags = ["oop"] 
+++

# Classes

In this activity, we will use classes to make two RPG characters match against each other.

## Instructions

* Open [character.js](starter/character.js) and update the `Character` class. It should instantiate an object with the following properties:

  * Name
  * Strength
  * hitPoints

* Create a `printStats()` class method that prints the name, strength, and hitPoints for a character.

* Create an `attack(opponent)` method that a character can use to deal damage (equal to their strength) to their opponent's hitPoints.  

* Create two instances of a character, giving them different names, strength, and hitPoints. 

* Using `setInterval`, make each character take turns attacking each other. 

* `printStats()` after each attack to visualize the battle.

* Use an `isAlive` method to check if each character has more than 0 hitPoints every turn. If either character has been defeated, stop the interval and end the game.

### BONUS

* Add validation to ensure that each character is provided the proper three arguments when created. If any of the arguments are not present, `throw` an error.

### Hints

* Before trying to make the characters take turns, try making one character attack another until the game is over.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```js
class Character {
  constructor(name, strength, hitPoints) {
    if (!name) {
      throw new Error("You are missing the name.");
    }
    if (!strength) {
      throw new Error("You are missing the strength.");
    }
    if (!hitPoints) {
      throw new Error("You are missing the hitPoints.");
    }
    this.name = name;
    this.strength = strength;
    this.hitPoints = hitPoints;
  }

  // method which prints all of the stats for a character
  printStats() {
    console.log(`Stats for ${this.name} are as following:`);
    console.log(`Each attack will do ${this.strength} damage.`);
    console.log(`${this.name} has ${this.hitPoints} hit points remaining!`);
    console.log("------------");
  }
  // method which determines whether or not a character's "hitpoints" are less then zero
  // and returns true or false depending upon the outcome
  isAlive() {
    if (this.hitPoints <= 0) {
      console.log(`${this.name} has been defeated!`);
      return false;
    }
    return true;
  }

  // method which takes in a second object and decreases their "hitPoints" by this character's strength
  attack(opponent) {
    console.log(`${this.name} hit ${opponent.name} for ${this.strength}`);
    opponent.hitPoints -= this.strength;
  }
}

// creates two unique characters using the "character" constructor
const grace = new Character("Grace", 30, 75);
const dijkstra = new Character("Dijkstra", 20, 105);

// This keeps track of whose turn it is
let graceTurn = true;

grace.printStats();
dijkstra.printStats();

const turnInterval = setInterval(() => {
  // If either character is not alive, end the game
  graceTurn = !graceTurn;

  if (!grace.isAlive() || !dijkstra.isAlive()) {
    clearInterval(turnInterval);
    console.log("Game over!");
  } else if (graceTurn) {
    grace.attack(dijkstra);
    dijkstra.printStats();
  } else {
    dijkstra.attack(grace);
    grace.printStats();
  }
}, 2000);
```
{{% /expand%}}