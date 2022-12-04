+++
title = "03. HTML Display 👩‍🎓👨‍🎓"
weight = 3
tags = ["html"] 
+++

# Display

For this activity you will work with a partner to resolve issues within the given code:

## Instructions

* Fix the given code so that:
  * All three list items in the navigation bar should display inline.
  * All three boxes are visible.
  * Each box appeara centered and on its own line.

If successfule your code should look like the following:

![Three list items are displayed on the right side of the navigation bar, corresponding with three boxes centered on the page.](../images/image-1.png)

## 💡 Hints

Which `display` value hides an element? 

---

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What is the CSS `visibility` property? How is it different from the `display` property?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
# style.css
```css
header {
  width: 100%;
  background-color: lightblue;
}

h2 {
  text-align: left;
}

ul {
  text-align: right;
  color: #ffffff;
}

/* List items in navigation bar */
li {
  /* Sets display to inline */
  display: inline;
  list-style-type: none;
  font-size: 40px;
}

/* Boxes */
img {
  /* Sets display to block */
  display: block;
  /*Sets margins to center elements*/
  margin: 0 auto;
}

#item-1 {
  background-color: #e0115f;
}

#item-2 {
  background-color: #0000ff;
}

#item-3 {
  background-color: #999900;
}

/* Box 3 */
#image-3 {
  /* Change display: none to display: block */
  display: block;
}
```

# index.html
```html
<!DOCTYPE html>
<html lang="en-GB">

  <head>
    <meta charset="UTF-8">
    <title>HTML Display</title>
    <link rel="stylesheet" href="./assets/css/style.css">
  </head>

  <body>
    <header>
      <h2>HTML Display</h2>
      <nav>
        <ul>
          <li id="item-1">LIST ITEM 1</li>
          <li id="item-2">LIST ITEM 2</li>
          <li id="item-3">LIST ITEM 3</li>
        </ul>
      </nav>
    </header>
    
    <section>
      <img src="./assets/images/image-1.png" alt="box with number 1"/>
      <img src="./assets/images/image-2.png" alt="box with number 2"/> 
      <img id="image-3" src="./assets/images/image-3.png" alt="box with number 3"/> 
    </section>
  </body>

</html>
```
{{% /expand%}}