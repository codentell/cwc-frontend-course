+++
title = "07. Mini Project 👩‍🎓👨‍🎓"
weight = 7
tags = ["oop"] 
+++

# Mini-Project: Word Guess

* As a user, I want to be able to play a word-guessing game from the command line.

## Acceptance Criteria

* It's done when the `Letter` and `Word` classes fulfill the tests in the `tests` folder.

* It's done when the user can run the command `npm start` to play the game.

---

## 💡 Hints

How do the tests suggest how each method and class should be written?

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* What does the `chalk` npm package do?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### index.js

```js
const Game = require("./lib/Game");

// Initialize a new Game object
const game = new Game();

// Start playing
game.play();
```
{{% /expand%}}