+++
title = "06. Setting Attributes 👩‍🎓👨‍🎓"
weight = 6
tags = ["web apis"] 
+++

# 🏗️ Use JavaScript to Set Attributes of HTML Element

Implement the following user story:

* As a web developer, I want all of my titles on a webpage to have the same styling. 

## Acceptance Criteria

* It's done when all the `<h4>` elements are selected and stored in a single variable.

* It's done when the text of each `<h4>` is set to `blue`, the font size is `30px`, and the text is `bold`.

* It's done when the padding to the left of the title is set to `10px` and the margin is set to `0`.

---

## 💡 Hints

How can you use a loop to iterate over a list of elements? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge to further your knowledge:

* How would using the `:scope` pseudo-class be useful when working with`querySelectorAll()`?

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

## index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Setting Attributes</title>
</head>
<body>
  <h1>Setting Attributes via JS</h1>
  <div id="main">
    <div class="sites">
      <div class="site1">
        <h4></h4>
        <a>
          <img>
        </a>
      </div>
      <div class="site2">
        <h4></h4>
        <a>
          <img>
        </a>
      </div>
      <div class="site3">
        <h4></h4>
        <a>
          <img>
        </a>
      </div>
    </div>
  </div>

  <script src="./assets/js/script.js"></script>
</body>
</html>
```

## script.js
```js


var sitesEl = document.querySelector(".sites");
var site1El = document.querySelector(".site1");
var site2El = document.querySelector(".site2");
var site3El = document.querySelector(".site3");
// Store all h4 elements in a variable
var siteTitles = document.querySelectorAll("h4");

site1El.children[0].textContent = "Site 1";
site1El.children[1].setAttribute("href", "https://google.com");
site1El.children[1].children[0].setAttribute("src", "assets/images/image_1.jpg");
site1El.children[1].children[0].setAttribute("alt", "man working");
site1El.children[1].children[0].setAttribute("style", "padding:10px;");

site2El.children[0].textContent = "Site 2";
site2El.children[1].setAttribute("href", "https://twitter.com");
site2El.children[1].children[0].setAttribute("src", "assets/images/image_2.jpg");
site2El.children[1].children[0].setAttribute("alt", "group brainstorm");
site2El.children[1].children[0].setAttribute("style", "padding:10px;");

site3El.children[0].textContent = "Site 3";
site3El.children[1].setAttribute("href", "https://instagram.com");
site3El.children[1].children[0].setAttribute("src", "assets/images/image_3.jpg");
site3El.children[1].children[0].setAttribute("alt", "women working");
site3El.children[1].children[0].setAttribute("style", "padding:10px;");

// Loop through all h4 elements to add styling 
for (var i = 0; i < siteTitles.length; i++) {
  siteTitles[i].setAttribute("style", "color: blue; font-weight: bolder; font-size: 30px; padding-left:10px; margin: 0");
}
```
{{% /expand%}}