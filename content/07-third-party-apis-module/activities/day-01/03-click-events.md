+++
title = "03. Click Events 👩‍🏫🧑‍🏫"
weight = 3
tags = ["third party apis"] 
+++


{{< tabs >}}
{{% tab name="index.html" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8" />
  <title>jQuery Click Events</title>

  <link rel="stylesheet" type="text/css" href="./assets/css/jass.css" />
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css" />
</head>

<body class="bg-dark text-light">
  
  <main>
    <h1>Click Events!</h1>
    <hr />

    <p>Click for an alert</p>
    <button id="alert-btn" class="btn btn-danger">Alert</button>
    <hr />

    <p>Click to toggle light theme</p>
    <button id="theme-btn" class="btn btn-info">Toggle Theme</button>
    <hr />

    <p>Click for the next winning lottery number</p>
    <button id="lottery-btn" class="btn btn-primary">Play Lottery</button>
    <span id="lottery-number"></span>
    <hr />

    <p>Click to refresh page</p>
    <button id="refresh-btn" class="btn btn-warning">
      Refresh Page
    </button>
  </main>

  <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>

  <script type="text/javascript" src="./assets/js/script.js">
  </script>
</body>

</html>
```
{{% /tab %}}
{{% tab name="style.css" %}}
```css
main {
  margin: 3rem auto;
  max-width: 90vw;
  width: 50ch;
}

h1 {
  font-size: 4rem;
}

p {
  margin-top: 1rem;
  margin-bottom: 0.5rem;
}

#lottery-number {
  font-size: 2rem;
}

```
{{% /tab %}}

{{% tab name="index.js" %}}
```js
var alertButtonEl = $('#alert-btn');
var themeButtonEl = $('#theme-btn');
var lotteryButtonEl = $('#lottery-btn');
var lotteryNumberEl = $('#lottery-number');
var refreshButtonEl = $('#refresh-btn');

// light theme state
var isDark = true;

// Click event causes alert "Hello World"
// Vanilla JS equivalent: `addEventListener`
alertButtonEl.on('click', function () {
  alert('Hello World');
});

// Click event causes alert light theme toggle
themeButtonEl.on('click', function () {
  if (isDark) {
    $('body').css({ 'background-color': '#d9e9e8', color: '#1a1a1a' });
    isDark = !isDark;
  } else {
    $('body').css({ 'background-color': '#1a1a1a', color: '#d9e9e8' });
    isDark = !isDark;
  }
});

// Click event causes random number
lotteryButtonEl.on('click', function () {
  var random = Math.floor(Math.random() * 100000000) + 10000000;
  console.log(random);
  lotteryNumberEl.text(random);
});

// Click event causes refresh
refreshButtonEl.on('click', function () {
  location.reload();
});

```
{{% /tab %}}
{{< /tabs >}}



