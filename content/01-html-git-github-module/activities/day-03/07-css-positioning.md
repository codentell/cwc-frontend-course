+++
title = "07. CSS Positioning 👩‍🎓👨‍🎓"
weight = 7
tags = ["html"] 
+++

# Positioning

Work with a partner to implement the following user story:

* As a developer, I want to use the CSS position property to change the layout of my page.

## Instructions

Fix the given code so that:

* `box 2` is positioned in the middle of `square 1` using relative positioning.
* `box 2` is positioned outside of the upper-right corner of `square 2` using absolute positioning.

Your solution must match the following image:

![Box 2 is positioned in the center of Square 1, while in Square 2, Box 2 is positioned outside the square.](../images/css-positioning.png)

## 💡 Hints

How does the CSS `position` property change the document's normal flow? 

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What is the `z-index` property? 

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

# index.html
```html
<!DOCTYPE html>
<html lang="en-GB">

  <head>
    <meta charset="UTF-8">
    <title>CSS Positioning</title>
    <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
  </head>

  <body>
    <header>
      <h1>CSS Positioning</h1>
    </header>

    <main>
      <section>
        <h2>Square 1: Relative Position</h2>
        <div class="container">
          <img src="./assets/images/image-1.png" alt="box with number 1"/>
          <img id="relative-box-2" src="./assets/images/image-2.png" alt="box with number 2"/>
          <img src="./assets/images/image-3.png" alt="box with number 3"/>
        </div>
      </section>

      <section>
        <h2>Square 2: Absolute Position</h2>
        <div class="container absolute-container">
          <img src="./assets/images/image-1.png" alt="box with number 1"/>
          <img id="absolute-box-2"src="./assets/images/image-2.png" alt="box with number 2"/>
          <img src="./assets/images/image-3.png" alt="box with number 3"/>
        </div>
      </section>
    </main>
  </body>

</html>
```
# style.css
```css
body {
  /* Sets the position of the body to relative */
  position: relative;
  margin: 0;
  padding: 0;
}

main {
  /* Adds padding to the top of the main element equal to height of fixed header */
  padding-top: 100px;
}

h1,
h2,
h3 {
  text-align: center;
}

img {
  display: block;
}

header {
  /* Sets header position to fixed */
  position: fixed;
  /* Positions header 0 length from top of page */
  top: 0;
  /* Sets the stack order of the header */
  z-index: 2;
  width: 100%;
  height: 100px;
  border-bottom: 10px solid darkblue;
  background-color: lightblue;
}

/* Square 1 and 2 */
.container {
  width: 600px;
  height: 600px;
  margin: 20px auto;
  border: 15px solid black;
}

/* Square 2 */
.absolute-container {
  /* Sets parent element to relative */
  position: relative;
}

/* Box 2 in Square 1 */
#relative-box-2 {
  position: relative;
  /* Offsets box 200px from left to center it */
  left: 200px;
}

/* Box 2 in Square 2 */
#absolute-box-2 {
  /* Sets position to absolute */
  position: absolute;
  /* Positions box zero length from top of parent container */
  top: 0;
  /* Positions box 700px from left of parent container */
  left: 700px;
}
```
{{% /expand%}}