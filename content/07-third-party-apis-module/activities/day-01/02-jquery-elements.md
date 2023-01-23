+++
title = "02. jQuery Element 👩‍🎓👨‍🎓"
weight = 2
tags = ["third party apis"] 
+++

# 📖 Create HTML Elements with jQuery

Implement the following user story:

* As a user, I want to be greeted with a quote by an author when I open the page.

## Acceptance Criteria

* It's done when the page dynamically displays a quote by an author and the author's name on load.

## 📝 Notes

Refer to the following documentation:

[jQuery API documentation](https://api.jquery.com/)

## Assets

The following image demonstrates the web application's appearance and functionality:

![A quote appears in blue text on a black background, with the author's name in white text on the next line.](../images/01-quote.png)

---

## 💡 Hints

* Don’t forget to add jQuery to `index.html` before you begin.

* Only use jQuery methods! Do NOT use any of the following vanilla JavaScript methods: `createElement`, `textContent`, or `appendChild`.

## 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge:

* How can we add event listeners using jQuery?

Use [Google](https://www.google.com) or another search engine to answer this question.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8">
    <title>jQuery DOM elements</title>
    <link rel="stylesheet" href="./assets/css/jass.css" />
    <link rel="stylesheet" href="./assets/css/style.css" />
    
  </head>
  <body class="bg-dark">

    <!-- We created an empty div. Note that there is no content inside. -->
    <div id="root" class="m-5"></div>
     
    <!-- Added link to the jQuery library -->
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>

    <script type="text/javascript" src="./assets/js/script.js">
    </script>
  </body>
</html>
```

### index.js
```js
// Select the existing DOM element, <div id="empty-div">, and assign to a new variable
var rootEl = $('#root');

// Create a `<p>` element to store the quote's author and assign to a new variable
var authorEl = $('<p>');

// Add text to the author element
authorEl.text('~ Carol Dweck');

// Add the class `plain` to the author element
authorEl.addClass('plain');

// Create a `<h1>` element and assign to new variable
var quoteEl = $('<h1>');

// Add a meaningful quote to the quote element
quoteEl.text(
  'Love Challenges, Be Intrigued by Mistakes, Enjoy Effort, and Keep Learning.'
);

// Apply the class `fancy` to the quote element
quoteEl.attr('class', 'fancy');

// Attach the author element to the quote element
quoteEl.append(authorEl);

// Append the quote element to the page
rootEl.append(quoteEl);
```
{{% /expand%}}