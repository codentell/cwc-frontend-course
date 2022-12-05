+++
title = "07. Mini Project 👩‍🎓👨‍🎓"
weight = 7
tags = ["css"] 
+++

# Mini-Project: CSS Snippet Cheat Sheet

In this activity, you will work with a group to build a webpage that will hold a collection of CSS snippets. What better way to learn CSS than to build a knowledge base of CSS?

## Instructions

The completed application should meet the following criteria:

* As a user, I can view a collection of labeled CSS snippets in a responsive grid.

* As a user, I can easily identify these CSS snippets by their headings.

* As a user, I can highlight a code snippet by clicking on it.

* As a user, I can view my application on a mobile device as well as a desktop.

### Specifications

* Must use semantic HTML elements and proper indentation.

* Use CSS variables to maintain clean and reusable values for a color scheme.

* Use flexbox and media queries to create a responsive grid layout.

* Each CSS snippet should have a card-like layout with the CSS syntax wrapped in an [HTML pre element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre).

* Each CSS snippet can easily be highlighted for copying on click using the [CSS user-select property](https://developer.mozilla.org/en-US/docs/Web/CSS/user-select).

* Must incorporate a background color using a [CSS linear-gradient function](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient).

* Must incorporate a bit of animation using the [CSS transition property](https://developer.mozilla.org/en-US/docs/Web/CSS/transition).

* You and your group can decide which CSS styles and colors you will use to design the application, but the app needs to be a responsive. Use the following images to gain an understanding of how the app should look at different screen sizes, from a layout perspective:

  * At size 992px and above, the app should resemble the following image:

    ![On a desktop, the application displays three CSS code snippets per row.](../images/01-app-desktop.png)

  * At size 768px and above, the app should resemble the following image:

    ![On a tablet, the application displays two CSS code snippets per row.](../images/02-app-tablet.png)

  * On mobile devices, anything under 768px, the app should resemble the following image:

    ![On a mobile device, the application displays one CSS code snippet per row.](../images/03-app-mobile.png)

### 💡 Hints

* The HTML `<pre>` element is very literal about spaces and indentation. To gain a better understanding of how to work with it, check out this article on [considerations for styling the pre tag](https://css-tricks.com/considerations-styling-pre-tag/).

### 🏆 Bonus

* Set this project up in your own GitHub repositories so that you can deploy and use it for future reference!

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
# index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Snippet Cheatsheet</title>
  <link rel="stylesheet" href="assets/css/reset.css" />
  <link rel="stylesheet" href="./assets/css/style.css" />
</head>

<body>


  <header>
    <h1 class="page-title">
      CSS Snippet Cheatsheet
    </h1>
    <p>
      Ever have trouble recalling the exact syntax for your favorite CSS code? Give it a permanent home and add it to
      this page! Select any snippet below and it'll automatically select all of the code for you to copy.
    </p>
  </header>

  <main>
    <section class="row justify-center">
      <div class="card-column">
        <figure class="card code-card">
          <h2 class="card-header">Flexbox Row</h2>
          <div class="card-body">
            <p>Use these three properties to create a Flexbox row layout.</p>
          </div>
          <!-- with the <pre> element, it counts all spaces literally, so proper code indentation cannot be applied in this case -->
          <pre class="code-block"><code>.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}</code></pre>
        </figure>
      </div>
      <div class="card-column">
        <figure class="card code-card">
          <h2 class="card-header">Flexbox Column</h2>
          <div class="card-body">
            <p>Use this to create a Flexbox column layout.</p>
          </div>
          <pre class="code-block"><code>.column {
  display: flex;
  flex-direction: column
}</code></pre>
        </figure>
      </div>

      <div class="card-column">
        <figure class="card code-card">
          <h2 class="card-header">CSS Grid Layout</h2>
          <div class="card-body">
            <p>Build a 12-column layout using CSS Grid</p>
          </div>
          <pre class="code-block"><code>.grid {
  display: grid;
  width: 100%;
  grid-template-columns: repeat(12, 1fr);
}</code></pre>
        </figure>
      </div>
      <div class="card-column">
        <figure class="card code-card">
          <h2 class="card-header">Linear Gradients</h2>
          <div class="card-body">
            <p>This will create a background linear gradient from top to bottom.</p>
          </div>
          <pre class="code-block"><code>.linear-gradient-background {
  background-image: linear-gradient(
    rgba(232, 102, 236, 0.3) 0%,
    rgba(232, 102, 236, 0.6) 100%
  );
}</code></pre>
        </figure>
      </div>
      <div class="card-column">
        <figure class="card code-card">
          <h2 class="card-header">Box Transition Glow</h2>
          <div class="card-body">
            <p>Use transition and box shadows to glow on hover.</p>
          </div>
          <pre class="code-block"><code>.code-card .card-header {
  border-radius: 8px;
  transition: all 0.5s ease-in-out;
}

.code-card:hover,
.code-card:hover .card-header {
  box-shadow: inset 0px 0px 8px rgba(232, 102, 236, 1), 0 0 15px rgba(232, 102, 236, 1);
}</code></pre>
        </figure>
      </div>

      <div class="card-column">
        <figure class="card code-card">
          <h2 class="card-header">Overlay Card with Title</h2>
          <div class="card-body">
            <p>Use position properties and negative margins to raise elements higher than their natural starting point.
            </p>
          </div>
          <pre class="code-block"><code>.card-header {
  position: relative;
  margin-top: -20px;
}</code></pre>
        </figure>
      </div>
    </section>
  </main>

  <footer>
    <h3>Made with <span role="img" aria-label="heart">❤️</span> and CSS</h3>
  </footer>

</body>

</html>
```

# reset.css
```css
*,
*:before,
*:after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  height: 100%;
}

body {
  min-height: 100%;
  line-height: 1;
  font-family: sans-serif;
}

​h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: 100%;
}

​input,
select,
option,
optgroup,
textarea,
button,
pre,
code {
  font-size: 100%;
  font-family: inherit;
}

​ol,
ul {
  list-style: none;
}
```

# style.css
```css
/* color scheme sourced from http://khroma.co/generator/ */
:root {
  --outer-space: #33393f;
  --bright-turquoise: #2aefcb;
  --gin: #e0eae4;
  --heliotrope: #e866ec;
}

/* set content highlight color and background */
::selection {
  background-color: var(--bright-turquoise);
  color: var(--outer-space);
}

html {
  /* set 1rem to 10px instead of native 16px to make it easier to calculate font-size values for the rest of the page (e.g. 1.6rem is 16px, 2.0rem is 20px, etc.) */
  font-size: 62.5%;
}

body {
  /* Sans Serif font stack is implemented to help select the best font for each type of computer operating system */
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /* set body font size to 1.75rem, which is 1.75x more than the font-size of 10px, making it 17.5px  */
  font-size: 1.75rem;
  line-height: 1.5;
  color: var(--gin);
  background-color: var(--outer-space);
}

h1,
h2,
h3,
h4,
h5,
h6 {
  margin-bottom: 0.625rem;
  color: var(--heliotrope);
  font-weight: 700;
  line-height: 1.1;
}

h1 {
  /* 4rem = 40px (4 * 10px) */
  font-size: 4rem;
}

h2 {
  font-size: 3.5rem;
}

h3 {
  font-size: 3rem;
}

h4 {
  font-size: 2.5rem;
}

h5 {
  font-size: 2rem;
}

h6 {
  font-size: 1.5rem;
}

p {
  margin-bottom: 1rem;
}

code {
  /* Monospace font stack is used for our code blocks to make it look more like code */
  font-family: Consolas, 'Andale Mono WT', 'Andale Mono', 'Lucida Console',
    'Lucida Sans Typewriter', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono',
    'Liberation Mono', 'Nimbus Mono L', Monaco, 'Courier New', Courier,
    monospace;
}

header {
  width: 96%;
  margin: 0 auto;
  padding: 2.5rem;
  text-align: center;
}

header h1.page-title {
  padding: 1rem 1.2rem;
  font-size: 4.5rem;
}

main {
  width: 96%;
  margin: 2rem auto;
}

footer {
  margin: 1.5rem;
  text-align: center;
}

/* create our main grid with flexbox, use negative margins to offset the padding on the .card-column class */
.row {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  margin-left: -1.5rem;
  margin-right: -1.5rem;
}

.justify-center {
  justify-content: center;
}

/* using a mobile-first approach, set base column width to be 100% and we'll update it using media queries for larger screen sizes */
.card-column {
  flex: 1 0 100%;
  padding: 1.5rem;
  /* when the screen resizes, make it so our columns don't jump in size */
  transition: flex-basis 500ms linear;
  margin-bottom: 1.5rem;
}

/* make each code card a flexbox column to align and justify content within it */
.code-card {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  min-height: 100%;
  padding: 2rem;
  color: var(--heliotrope);

  /* outline is like border, but on the outside of the box instead of inside */
  outline: 2px dashed var(--gin);
  outline-offset: -2px;
  transition: all 0.5s ease-in-out;
}

.code-card .card-header {
  /* use position and negative margins to move title of card over the card's outline and create an overlap effect */
  position: relative;
  margin: -4rem 0 1.5rem 0;
  padding: 0.5rem 1rem;
  background-color: var(--outer-space);
  color: var(--heliotrope);
  border: 2px solid var(--gin);
  border-radius: 8px;
  transition: all 0.5s ease-in-out;
}

/* set an outer and inner drop shadow on the card to create a glowing effect on hover */
.code-card:hover,
.code-card:hover .card-header {
  box-shadow: inset 0px 0px 8px var(--heliotrope), 0 0 15px var(--heliotrope);
}

/* each card's code block grows to the height of the largest code block on the page, making each card even in height */
.code-card .code-block {
  flex-grow: 1;
}

.code-card pre {
  /* set styles to make it so code wraps in <pre> instead of overflowing */
  white-space: pre-wrap;
  overflow: auto;
  tab-size: 4;
  padding: 1.2rem 1rem;
  color: var(--gin);
  border-radius: 8px;
  /* use linear-gradient() function to create a fading background  */
  background-image: linear-gradient(
    rgba(232, 102, 236, 0.3) 0%,
    rgba(232, 102, 236, 0.6) 100%
  );
  display: flex;
  align-items: center;
}

/* on <pre> click, select all contents so the code is highlighted */
.code-card pre:active {
  user-select: all;
}

/* using a mobile-first approach, use `min-width` values going from narrow -> wide for a responsive design */
@media screen and (min-width: 768px) {
  /* on tablets, set columns to only be 50% of the width and not grow */
  .card-column {
    flex: 0 0 50%;
    max-width: 50%;
  }

  /* select the last child to grow to full width if it has space to grow */
  .card-column:last-child {
    flex-grow: 1;
  }
}

/* media query for larger screens */
@media screen and (min-width: 992px) {
  header {
    width: 75%;
  }

  .card-column {
    flex: 0 0 33.333%;
    max-width: 33.333%;
  }
}
```

{{% /expand%}}