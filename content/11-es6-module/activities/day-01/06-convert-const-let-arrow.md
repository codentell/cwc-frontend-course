+++
title = "06. Convert Const Let 👩‍🎓👨‍🎓"
weight = 7
tags = ["es6"] 
+++

# 🏗️ Convert to ES6 Syntax

Work with a partner to implement the following user story:

* As a developer, I want to be able to recognize and implement newer ES6 syntax.

## Acceptance Criteria

* It's done when I understand the application's functionality in `index.html` and `index.js`. 

* It's done when I have converted `var` to `const` or `let` based on the use case.

* It's done when I have converted all functional expressions to arrow functions.

## 💡 Hint

When is it not suitable to use arrow functions?

## 🏆 BONUS

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* Take one of the previous exercises and convert it to ES6 syntax. How can you shorten arrow functions even further?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```js
const $root = document.querySelector("#root");

let score;
let targetScore;

const makeGuess = () => {
  const $score = document.querySelector("#root p");
  $score.textContent = "Score: " + score + " | " + "Target: " + targetScore;

  if (score > targetScore) {
    alert("You lost this round!");
    playRound();
  } else if (score === targetScore) {
    alert("You won this round!");
    playRound();
  }
};

const Crystal = function(color) {
  this.element = document.createElement("div");
  this.element.className = "crystal " + color;
  this.value = 0;

  this.element.addEventListener(
    "click",
    () => {
      score += this.value;
      makeGuess();
    },
    false
  );
};

Crystal.prototype.render = function(target) {
  this.value = Math.floor(Math.random() * 15) + 1;
  target.appendChild(this.element);
};

const crystals = [
  new Crystal("red"),
  new Crystal("blue"),
  new Crystal("green")
];

const playRound = () => {
  const fragment = document.createDocumentFragment();
  const $score = document.createElement("p");
  targetScore = Math.floor(Math.random() * 50) + 25;
  score = 0;
  $score.textContent = "Score: " + score + " | " + "Target: " + targetScore;
  crystals
    .sort(() => 0.5 - Math.random())
    .forEach(crystal => crystal.render(fragment));
  fragment.appendChild($score);
  $root.innerHTML = "";
  $root.appendChild(fragment);
};

playRound();
```
{{% /expand%}}