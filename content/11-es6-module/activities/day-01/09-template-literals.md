+++
title = "09. Template Literals 👩‍🎓👨‍🎓"
weight = 10
tags = ["es6"] 
+++

# 🏗️ Implement Template Literals

Implement the following user story:

* As a developer, I want to know how to use template strings render HTML.

## Acceptance Criteria

* It's done when I have created a `music` object in `starter/index.js`.

* It's done when I have added `title`, `artist`, and `album` properties to the `music` object.

* It's done when I have used template strings in the `div` tags to output data from the `music` object.

* It's done when I open `index.html` and see the results.

## 💡 Hint

* Can we use template strings in place of string concatenation?

## 🏆 BONUS

If you have completed this activity, work through the following challenge to further your knowledge:

* It's easy to get confused about which syntax belongs to which technology. The dollar sign (`$`) is used a lot in JavaScript. What are some other places you have seen the dollar sign used?

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Template Literals</title>
</head>
<body>
  <div id="music"></div>

<script type="text/javascript" src="index.js"></script>
</body>
</html>
```


### index.js
```js
const music = {
  title: "The Less I Know The Better",
  artist: "Tame Impala",
  album: "Currents"
};

// write code between the <div> tags to output your objects data
const songSnippet = `
  <div class="song">
     <h2>${music.title}</h2>
     <p class="artist">${music.artist}</p>
     <p class="album">${music.album}</p>
  </div>
`;
const element = document.getElementById("music");
element.innerHTML = songSnippet;
```
{{% /expand%}}