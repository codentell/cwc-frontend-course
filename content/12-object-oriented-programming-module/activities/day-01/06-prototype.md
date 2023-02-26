+++
title = "06. Prototypes 👩‍🎓👨‍🎓"
weight = 6
tags = ["oop"] 
+++

# Character Creation with Prototypes

In this activity, you will generate RPG characters using Objects and prototypes.

## Instructions

* Over the course of this activity, you are going to be using constructors to create simplistic characters for use within a very basic role-playing game (RPG).

* Each character created using your constructor should have the following properties:

  * Name: The character's name --> String

  * Profession: What the character does for a living --> String

  * Age: The character's age --> Number

  * Strength: Abstraction for how strong the character is --> Number

  * HitPoints (HPs): Abstraction for how much health the character has --> Number

  * PrintStats: Function which prints all of a character's properties to the screen

* Once you have created your constructor, create two new characters and print their properties to the screen.

* Now add three methods onto it via the prototype.

  * IsAlive: Function that prints whether or not this character is alive by looking into their hitpoints and determining whether they are above or below zero.

  * Attack: Function that takes in a second character and subtracts this character's strength from their hitpoints.

  * LevelUp: Function that increases this character's Age by 1, their Strength by 5, and their HitPoints by 25.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```js
// constructor function which can take in a series of values and create objects
// with the properties contained inside
function Character(name, profession, age, strength, hitpoints) {
  this.name = name;
  this.profession = profession;
  this.age = age;
  this.strength = strength;
  this.hitpoints = hitpoints;
}
// method which prints all of the stats for a character
Character.prototype.printStats = function () {
  console.log(
    `Name: ${this.name}\nProfession: ${this.profession}\nAge: ${this.age}\nStrength: ${this.strength}\nHitPoints: ${this.hitpoints}`
  );
  console.log('\n-------------\n');
};

// method which determines whether or not a character's "hitpoints" are less than zero
// and returns true or false depending upon the outcome
Character.prototype.isAlive = function () {
  if (this.hitpoints > 0) {
    console.log(`${this.name} is still alive!`);
    console.log('\n-------------\n');
    return true;
  }
  console.log(`${this.name} has died!`);
  return false;
};

// method which takes in a second object and decreases their "hitpoints" by this character's strength
Character.prototype.attack = function (character2) {
  character2.hitpoints -= this.strength;
};

// method which increases this character's stats when called
Character.prototype.levelUp = function () {
  this.age += 1;
  this.strength += 5;
  this.hitpoints += 25;
};

// creates two unique characters using the "character" constructor
const warrior = new Character('Crusher', 'Warrior', 25, 10, 75);
const rogue = new Character('Dodger', 'Rogue', 23, 20, 50);

warrior.printStats();
rogue.printStats();

rogue.attack(warrior);
warrior.printStats();
warrior.isAlive();

rogue.levelUp();
rogue.printStats();
```
{{% /expand%}}