+++
title = "02. for...of 👩‍🎓👨‍🎓"
weight = 2
tags = ["es6"] 
+++

# 🏗️ Implement and Use for...of Loops

Implement the following user story:

* As a developer, I want to be able to use `for...of` loops to iterate through data inside objects.

## Acceptance Criteria

* It's done when I have selected all the inside `#songs` elements in the `html`.

* It's done when I have iterated through the song collection with a `for...of` loop and added a `class` of `red` to each element.

## 💡 Hint

What part of the object is essential in setting up the iteration of a `for...of` loop?

## 🏆 BONUS

If you have completed this activity, work through the following challenge to further your knowledge:

* How could you iterate through deeply nested objects?

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
  <link href="style.css" rel="stylesheet" type="text/css">
  <title>For...of</title>
</head>

<body>
  <h2>Spotify Global Top 50</h2>
  <ul id="songs">
    <li>1. Fast by Sueco the Child</li>
    <li>2. Old Town Road - Remix by Lil Nas X</li>
    <li>3. Wrong by Luh Kel </li>
    <li>4. Piece Of Your Heart by MEDUZA</li>
    <li>5. Kill This Love by BLACKPINK</li>
    <li>6 bad guy by Billie Eilish</li>
    <li>7. Verte Ir by DJ Luian</li>
    <li>8. Beef FloMix by Flo Milli</li>
    <li>9. Avengers: Endgame by Jared Moreno Luna</li>
    <li> 10. Old Town Road by Lil Nas X</li>
  </ul>
  <script type="text/javascript" src="index.js"></script>
</body>

</html>
```


### index.js 
```js
const songs = document.querySelectorAll("ul > li");

for (const song of songs) {
  song.classList.add("green");
}




```

### style.css

```css
.green {
  color: green;
}
```
{{% /expand%}}

