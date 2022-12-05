+++
title = "03. CSS Selectors 👩‍🏫🧑‍🏫"
weight = 3
tags = ["css"] 
+++



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
          <p>A successful web developer is one that knows that there's always room to grow and learn. You may not use
            every single tool that's offered to you, but it's always good to know that certain tools exist. Check out
            these resources to broaden your knowledge:</p>
          <ul>
            <li>
              Mozilla Developer Network's documentation on <a
                href="https://developer.mozilla.org/en-US/docs/Web/CSS">Cascading Style Sheets (CSS)</a> is a good
              resource for all things CSS and web development in general.
            </li>
            <li>Our own <a href="./assets/css/reset.css">reset.css</a> file shows how to set default browser styles.
            </li>
            <li>Another reset style sheet called
              <a href="https://necolas.github.io/normalize.css/8.0.1/normalize.css">normalize.css</a> is popular in the
              web development community</li>
            <li>Our own <a href="./assets/css/style.css">style.css</a> file shows how we've designed the page we're
              reading!
            </li>

            <li>The popular blog, <a href="https://css-tricks.com/">CSS Tricks,</a> has a lot of articles and resources
              to make you a better developer!
            </li>

          </ul>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil natus recusandae amet nostrum odit, ut unde
            non sint, quia sed inventore odio, delectus iure! Eligendi vitae fuga blanditiis accusamus tempore! Lorem
            ipsum dolor sit amet consectetur adipisicing elit. Consectetur, nisi, saepe quas sint consequuntur esse
            voluptatum, dolores dolor aspernatur neque laborum dolorum dolorem repudiandae. Dignissimos eveniet sequi
            corporis tempore ullam!</p>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil natus recusandae amet nostrum odit, ut unde
            non sint, quia sed inventore odio, delectus iure! Eligendi vitae fuga blanditiis accusamus tempore!</p>
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

article li {
  margin: 5px 0;
}

/* Use :nth-child() to select every even list item */
article ul li:nth-child(even) {
  background-color: #b9c6ae;
  color: #13293d;
}

/* Use adjacent sibling combinator (+) to select all <p> elements that come immediately after a <ul> element inside of an <article> element */
article ul + p {
  background-color: #13293d;
  color: #fff;
}

/* Use child combinator (>) with a wildcard selector (*) to select every single element that is a direct descendant (or child) of any <div> element in an <article> element */
article div > * {
  padding: 20px;
  border: 4px solid #b9c6ae;
}

footer {
  display: flex;
  justify-content: center;
  padding: 2%;
  background-color: #13293d;
  color: #fff;
}

@media screen and (max-width: 768px) {
  header {
    flex-direction: column;
  }

  main {
    max-width: 1200px;
  }
}
```