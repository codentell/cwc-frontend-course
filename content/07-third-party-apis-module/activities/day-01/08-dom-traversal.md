+++
title = "08. Dom Traversal 👩‍🎓👨‍🎓"
weight = 8
tags = ["third party apis"] 
+++

# 📖 Implement Tic-Tac-Toe Automation

Work with a partner to implement the following user story:

* As a game developer, I want to programmatically change the board style.

* As a game developer, I want to programmatically add the winning move.

## Acceptance Criteria

* It's done when the board's tiles are automatically styled on page load.

* It's done when the X player is blocked from winning.

* It's done when the O player has won.

## 📝 Notes

Refer to the following documentation: 

[jQuery Docs on Traversing](https://api.jquery.com/category/traversing) 

[jQuery Docs on Markup Changes](https://api.jquery.com/text/) 

## Assets

The following image demonstrates the web application's appearance and functionality:

![A Tic-Tac-Toe board shows that the O player has won the game.](../images/08-solution-screenshot.png)

---

## 💡 Hint 

* The starting point for all the the traversals in this activity must begin at the `<main id="root">`, which has been assigned for you as `rootEl`.
  
## 🏆 Bonus 

If you have completed the activity and want to further your knowledge, work through the following challenge with your partner:

* What are some alternative methods to traverse up and down the DOM tree? Use [Google](https://www.google.com) or another search engine to answer this question.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8" />
  <title>jQuery Tic Tac Toe</title>
  <link rel="stylesheet" type="text/css" href="./assets/css/jass.css">
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
</head>

<body class="bg-dark text-light">
  <main id="root">
    <h1 class="text-center pb-5">Tic Tac Toe</h1>

    <!-- row one -->
    <ul>
      <li class="item-a1">O</li>
      <li class="item-b1"></li>
      <li class="item-c1">X</li>
    </ul>

    <!-- row two -->
    <ul>
      <li class="item-a2">O</li>
      <li class="item-b2">X</li>
      <li class="item-c2"></li>
    </ul>

    <!-- row three -->
    <ul>
      <li class="item-a3"></li>
      <li class="item-b3"></li>
      <li class="item-c3"></li>
    </ul>
  </main>

  <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script type="text/javascript" src="./assets/js/script.js"></script>
</body>

</html>
```

### index.js
```js
// Ensure the document is rendered when manipulating DOM elements
// Assemble: Create/select DOM elements
var rootEl = $('#root');

// Starting from the root element, `<main id="root">`, select all the boxes and change the background color to white.
rootEl.children('ul').children().css('background-color', 'white');

// Select the last `<ul>` or the third row.
// Long traverals can be segmented to provide better readability.
var rowThree = rootEl.children('ul').eq(2);

// Select the children of the `<ul>`, then select the first box and add the 'O'.
rowThree.children().eq(0).text('O');
```
{{% /expand%}}