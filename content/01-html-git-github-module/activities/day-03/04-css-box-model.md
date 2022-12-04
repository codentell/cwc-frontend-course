+++
title = "04. CSS Box Model 👩‍🏫🧑‍🏫"
weight = 4
tags = ["html"] 
+++

## Folder Structure
```bash
04-Ins-CSS-box-model
├── assets
│      ├──css
│      │   └── style.css
│      └── images
│          ├── image-1.png
│          ├── image-2.png
│          ├── image-3.png
│          └── image-4.png
└── index.html
```

## style.css
```css
header {
  height: 100px;
  width: 100%;
  /* Sets border to bottom only */
  border-bottom: 10px solid darkblue;
  background-color: #999900;
}

section {
  width: 70%;
  /* Sets top and bottom margin to 20px. Auto will center element */
  margin: 20px auto;
  border-bottom: 5px solid darkblue;
  background-color: #ffffd4;
}

h1 {
  text-align: center;
  line-height: 100px;
}

h2 {
  /* Sets bottom margin to 0 */
  margin-bottom: 0;
}

h3 {
  /* Sets top margin to 0 */
  margin-top: 0;
}

.example-box {
  /* Shortcut method sets top and bottom padding to 20px and left and right to 40px */
  padding: 20px 40px;
}

.image-padding {
  /* Sets padding on all sides to 20px */
  padding: 20px;
  background-color: #999900;
}

.image-border {
  /* Sets border on all sides */
  border: 10px solid darkblue;
}

.image-margin {
  /* Sets all sides to 20px */
  margin: 20px;
}
```

## index.html
```html
<!DOCTYPE html>
<html lang="en-GB">

  <head>
    <meta charset="UTF-8">
    <title>CSS Box Model</title>
    <link rel="stylesheet" href="./assets/css/style.css">
  </head>

  <body>
    <header>
      <h1>HTML Box Model</h1>
    </header>
    
    <section>
      <div class="example-box">
        <h2>Content Area</h2>
        <h3>is made up of the width and height of the content</h3>
        <img src="./assets/images/image-1.png" alt="box with number 1"/>
        <h4>The content has a width of 200px</h4>
        <h4>The content has a height of 200px</h4>
      </div>
    </section>

    <section>
      <div class="example-box">
        <h2>Padding Area</h2>
        <h3>extends the content area to include padding around it</h3>
        <img class="image-padding" src="./assets/images/image-1.png" alt="box with number 1"/>
        <h4>The content has a width of 200px</h4>
        <h4>The content has a height of 200px</h4>
        <h4>The padding on each side of the content is 20px</h4>
      </div>
    </section>

    <section>
      <div class="example-box">
        <h2>Border Area</h2>
        <h3>extends the content area and padding to include border around it</h3>
        <img class="image-padding image-border" src="./assets/images/image-1.png" alt="box with number 1"/>
        <h4>The content has a width of 200px</h4>
        <h4>The content has a height of 200px</h4>
        <h4>The padding on each side of the content is 20px</h4>
        <h4>The border on each side is 10px</h4>
      </div>
    </section>

    <section>
      <div class="example-box">
        <h2>Margin Area</h2>
        <h3>extends the content area, padding, and border to include the margin around it</h3>
        <img class="image-padding image-border image-margin" src="./assets/images/image-1.png" alt="box with number 1"/>
        <img class="image-padding image-border image-margin" src="./assets/images/image-1.png" alt="box with number 1"/>
        <h4>The content has a width of 200px</h4>
        <h4>The content has a height of 200px</h4>
        <h4>The padding on each side of the content is 20px</h4>
        <h4>The border on each side is 10px</h4>
        <h4>The margin on each side is 20px.</h4>
        <h4>Total width of each box = 300px (200px + 20px + 20px + 10px + 10px + 20px + 20px)</h4>
        <h4>Total height of each box = 300px (200px + 20px + 20px + 10px + 10px + 20px + 20px)</h4>
      </div>
    </section>
      
  </body>

</html>

```