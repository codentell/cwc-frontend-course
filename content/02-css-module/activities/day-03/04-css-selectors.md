+++
title = "04. CSS Selectors 👩‍🎓👨‍🎓"
weight = 4
tags = ["css"] 
+++

# 📖 Implement an Icon for Downloadable Style Sheets

Work with a partner to implement the following user story:

* As a user, I want to see an icon next to every `<a>` element that has a link to a downloadable CSS file in its `href` attribute.

## Instructions

* Add a 📝 emoji to any link to a CSS file.
  * Should be added only using CSS


Your web application should look like the following image once complete:

![The updated page shows an emoji next to each link that takes you to a CSS file.](../images/01-selector-complete.png)

### 💡 Hints

* How can you target a file type by its file extension (i.e., `.css`, `.html`, `.md`, etc.)?

Refer to the following documentation: 

[MDN Web Docs on attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

### 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge with your partner:

* How do selectors affect CSS performance?

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
# index.html

```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Advanced Selectors with CSS</title>
  <link rel="stylesheet" href="./assets/css/reset.css" />
  <link rel="stylesheet" href="./assets/css/style.css" />
</head>

<body>
  <header>
    <h1>The CSS Blog</h1>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
        <li><a href="#">Resources</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section>
      <article>
        <h2>A List of Learning Resources</h2>
        <div>
          <p>
            A successful web developer is one that knows that there's always room to grow and learn. You may not use every single tool that's offered to you, but it's always good to know that certain tools exist. Check out these resources to broaden your knowledge:
          </p>
          <ul>
            <li>
              Mozilla Developer Network's documentation on <a href="https://developer.mozilla.org/en-US/docs/Web/CSS">Cascading Style Sheets (CSS)</a> is a good
              resource for all things CSS and web development in general.
            </li>
            <li>
              Our own <a href="./assets/css/reset.css">reset.css</a> file shows how to set default browser styles.
            </li>
            <li>Another reset style sheet called <a href="https://necolas.github.io/normalize.css/8.0.1/normalize.css">normalize.css</a> is popular in the
              web development community
            </li>
            <li>Our own <a href="./assets/css/style.css">style.css</a> file shows how we've designed the page we're reading!
            </li>

            <li>The popular blog, <a href="https://css-tricks.com/">CSS Tricks,</a> has a lot of articles and resources to make you a better developer!
            </li>

          </ul>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil natus recusandae amet nostrum odit, ut unde non sint, quia sed inventore odio, delectus iure! Eligendi vitae fuga blanditiis accusamus tempore! Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur, nisi, saepe quas sint consequuntur esse voluptatum, dolores dolor aspernatur neque laborum dolorum dolorem repudiandae. Dignissimos eveniet sequi
            corporis tempore ullam!
          </p>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil natus recusandae amet nostrum odit, ut unde non sint, quia sed inventore odio, delectus iure! Eligendi vitae fuga blanditiis accusamus tempore!
          </p>
        </div>
      </article>
    </section>
  </main>

  <footer>
    <span>Thanks for visiting!</span>
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
body {
  display: flex;
  flex-direction: column;
  line-height: 1.3;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1%;
  background-color: #13293d;
  color: #fff;
}

h1 {
  font-size: 200%;
}

h2 {
  margin: 2% 0;
  font-size: 250%;
}

nav ul {
  display: flex;
  justify-content: space-between;
  min-width: 300px;
}

nav a {
  color: #b9c6ae;
  font-weight: bold;
  text-decoration: none;
}

nav a:hover {
  color: #fff;
}

main {
  display: flex;
  flex: 1 1 0;
  max-width: 96%;
  margin: 2% auto;
}

article {
  border-bottom: 1px solid #13293d;
}

article p {
  margin: 2% 0;
  font-size: 110%;
}

article ul {
  margin-left: 5%;
  font-size: 110%;
  list-style: circle;
}

footer {
  display: flex;
  justify-content: center;
  padding: 2%;
  background-color: #13293d;
  color: #fff;
}

/* TODO: Add code here to select all <a> elements that link to a file with a `.css` extension */

@media screen and (max-width: 768px) {
  header {
    flex-direction: column;
  }

  main {
    max-width: 1200px;
  }
}
```


{{% /expand%}}