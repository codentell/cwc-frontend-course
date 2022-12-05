+++
title = "06. CSS Variables 👩‍🎓👨‍🎓"
weight = 6
tags = ["css"] 
+++

# 🏗️ Implement CSS Variables in Style Sheet

Work with a partner to implement the following user story:

* As a developer, I want to manage CSS values that are used in multiple CSS rules in a more efficient manner.

## Instructions

* Create two CSS Variables:
  * One for any repeated color value
  * One for any repeated border radius value

### 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge with your partner:

* What does the term DRY mean in web development?

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```html
<!DOCTYPE html>
<html>

<head>
  <title>CSS Box Styling</title>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link rel="stylesheet" type="text/css" href="./assets/css/reset.css">
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css" />
</head>

<body>
  <!-- Header -->
  <header>
    <h1>Welcome to the store!</h1>
    <p>
      Add some box styling to the product cards to make them POP!
    </p>
  </header>

  <!-- Navbar -->
  <nav>
    <a href="#">Camera</a>
    <a href="#">Tablet</a>
    <a href="#">Toilet Paper</a>
    <a href="#">Wooden Spoons</a>
  </nav>

  <!-- Body -->
  <main>
    <!-- Product Cards -->
    <div class="products">
      <section class="card">
        <header>Camera</header>
        <img src="./assets/images/camera.jpg" alt="camera" />
        <p>Price: $300</p>
      </section>
      <section class="card">
        <header>Tablet</header>
        <img src="./assets/images/tablet.jpg" alt="tablet" />
        <p>Price: $150</p>
      </section>
      <section class="card">
        <header>Toilet Paper</header>
        <img src="./assets/images/toilet-paper.jpg" alt="toilet paper" />
        <p>Price: $30</p>
      </section>
      <section class="card">
        <header>Wooden Spoons</header>
        <img src="./assets/images/wooden-spoons.jpg" alt="wooden spoons" />
        <p>Price: $10</p>
      </section>
    </div>
  </main>

  <!-- Footer -->
  <footer>
    <h3>
      Open Chrome DevTools --> Toggle device toolbar --> Resize the browser
      window!
    </h3>
  </footer>
</body>

</html>
```

# reset.css
```css
* {
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

h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: 100%;
}

input,
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

ol,
ul {
  list-style: none;
}


```

# style.css
```css
/* Create CSS variables at the root of the document to be used throughout the style sheet */
:root {
  --white: #fff;
  --dark-blue: #13293d;
  --tan: #d8a47f;
  /* You can use it with any value that is repeated throughout the sheet */
  --border-radius: 50px;
}

body {
  font-size: 16px;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  justify-content: flex-start;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 10px;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

header {
  padding: 40px;
  text-align: center;
  /* Refer to CSS values by the name of the custom property we assigned it */
  background: var(--dark-blue);
  color: var(--white);
}

nav {
  display: flex;
  background-color: var(--tan);
}

nav a {
  color: var(--dark-blue);
  padding: 14px 20px;
  text-decoration: none;
  text-align: center;
}

nav a:hover {
  background-color: var(--white);
  color: var(--dark-blue);
}

main {
  display: flex;
  flex-wrap: wrap;
}

footer {
  width: 100%;
  bottom: 0;
  padding: 20px;
  text-align: center;
  background: var(--dark-blue);
  color: var(--white);
  margin-top: auto;
}

.products {
  flex: 1;
  background-color: var(--white);
  padding: 50px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.card {
  border-style: solid;
  border-width: 1px;
  border-radius: var(--border-radius);
  padding: 10px;
  flex: 0 0 300px;
  transform: rotate(8deg);
  box-shadow: 10px 10px 5px #aaaaaa;
  margin: 20px;
}

.card > header {
  /* This is the same as `border-radius: 50px 50px 0 0 */
  border-radius: var(--border-radius) var(--border-radius) 0 0;
  padding: 20px;
}

.card > p {
  text-align: center;
}

.card > img {
  width: 100%;
}

@media screen and (max-width: 768px) {
  main,
  nav {
    flex-direction: column;
  }
}
```
{{% /expand%}}