+++
title = "04.  HTML CSS Layout 👩‍🎓👨‍🎓"
weight = 4
tags = ["html"] 
+++

# CSS Styled Bio Page

## Instructions:

* Unzip the folder provided to you (or copy and paste the contents outside).
* Use the command line to make a folder called `css`.
* Use the command line to make a file called `style.css` inside of the `css` folder.
* Reference the `style.css` in your `html-bio-with-css.html` file. You do this by placing `<link rel="stylesheet" type="text/css" href="css/style.css">` inside the `<head>` tag.
* Style the example on the projector.
  * Add a `class` called "container" on the `div` tag. For example: `<div class="container">`.
  * Add an `id` called "main-bio" for the first `section` tag.
  * Add an `id` called "contact-info" for the second `section` tag.
  * Add an `id` called "bio-image" for the bio image.
* Style specs:
  * `body`
    * The background color is `#efeee7`.
    * The font used is `Georgia,"Times New Roman",Times,serif;`.
    * The font color is `#333333`.
    * Be sure to zero out the body margins and padding so the page is flush to the top of the page:
      ```css
      body {
        margin: 0;
        padding: 0;
      }
      ```
  * `header`
    * The background color is `#333333`.
  * `h1`
    * The font color is `#eee`.
    * The font size is `28px`.
    * Look at the example on the screen, and eyeball the padding and/or margins and positioning of the text.
  * `h2`
    * The font size is `24px`
  * Make the container have a width of 1,024 pixels and center it. You do this using `margin: 0 auto;`.
  * Make `#main-bio`, `#contact-info`, `#bio-image` all `float: left`.
  * Make the `#bio-image` have a width of 200 pixels.
  * Be sure to include `alt` text in all images
  * `#main-bio` should have a width of `70%`.
    * Add margins to the image, so there is distance between it and the bio text.
  * `#contact-info` should have a width of `30%`.
  * Adjust the line height, so it is 1.5 times the size of the font.
  * Make the link color `#d21034`.

* If you forgot how to write the CSS properties, you can reference all CSS properties here: <https://developer.mozilla.org/en-US/docs/Web/CSS/Reference>.

## BONUS:

  * Stage, commit, and push this new file to Github.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

# style.css
```css
/**
 First External CSS Stylesheet
 **/

/*
Each of these CSS elements is associated with an HTML Element, Class, or ID.
Flip between this CSS file and the HTML to see how things line up.
Experiment with deleting lines of code from the CSS to see how it affects the webpage when you refresh in the browser.
*/

body {
  padding: 0;
  margin: 0;
  font-family: Georgia, "Times New Roman", Times, serif;
  font-size: 18px;
  line-height: 150%;
  color: #333;
  background: #efeee7;
}

header {
  background: #333;
}

h1 {
  padding: 20px 0;
  margin: 0;
  margin-bottom: 20px;
  font-size: 28px;
  color: #eee;
  text-align: center;
}

h2 {
  font-size: 24px;
}

a {
  color: #d21034;
}

.container {
  width: 1024px;
  margin: 0 auto;
}

#main-bio,
#contact-info,
#bio-image {
  float: left;
}

#main-bio {
  width: 70%;
}

#contact-info {
  width: 30%;
}

#bio-image {
  width: 200px;
  height: 200px;
  margin-right: 20px;
}

```

# html-bio-with-css.html
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>CSS Stylesheets with Relative Paths</title>

  <!-- This line is money! It points your HTML to the CSS file. -->
  <!-- Notice the "relative" pathway? It matches a file inside our current directory's "assets" folder. Open it to see our style rules. -->
  <link rel="stylesheet" type="text/css" href="css/style.css">

</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```




{{% /expand%}}