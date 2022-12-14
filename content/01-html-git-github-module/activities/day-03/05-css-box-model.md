+++
title = "05.  CSS Box Model ð©âðð¨âð"
weight = 5
tags = ["html"] 
+++


## Folder Structure
```bash
05-Stu-css-box-model
âââ assets
â      âââcss
â      â   âââ style.css
â      âââ images
â          âââ image-1.png
â          âââ image-2.png
â          âââ image-3.png
â          âââ image-4.png
âââ index.html
```

# Box Model

Work with a partner to implement the following user story:

* As a developer, I want to use the CSS box model properties to position four boxes inside a frame.
  
## Instructions

* Correct the code so that each box has a defined:
  * `padding` property
  * `margin` property
  * `border` property

Your solution should match the following image:

![Four numbered, differently colored boxes appear evenly spaced inside a larger box.](../images/css-box-model.png)

## ð Notes

Refer to the documentation: 

[MDN Web Docs on CSS basic box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model)

[MDN Web Docs on padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)

[MDN Web Docs on margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)

[MDN Web Docs on border](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

## ð¡ Hints

How can we use the `margin` property to define space between elements?

## ð Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* What is the CSS `float` property?

Use [Google](https://www.google.com) or another search engine to research this.

---



## â Solutions 
{{%expand "Solutions Click Here" %}}
# style.css
```css
section {
  width: 600px;
  height: 600px;
  text-align: center;
  border: 15px solid black;
}

img {
  width: 200px;
  height: 200px;
  background-color: lightblue;
  /* Margin property */
  margin: 20px;
  /* Padding property */
  padding: 20px;
  /* Border property */
  border: 9px solid darkblue;
}
```

# index.html
```html
<!DOCTYPE html>
<html lang="en-GB">

  <head>
    <meta charset="UTF-8">
    <title>HTML Box Model</title>
    <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
  </head>

  <body>
    <section>
      <img src="./assets/images/image-1.png" alt="box with number 1"/>
      <img src="./assets/images/image-2.png" alt="box with number 2"/>
      <img src="./assets/images/image-3.png" alt="box with number 3"/>
      <img src="./assets/images/image-4.png" alt="box with number 4"/>
    </section>
  </body>

</html>

```
{{% /expand%}}