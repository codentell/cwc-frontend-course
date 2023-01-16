+++
title = "01. Local Storage Counter 👩‍🏫🧑‍🏫"
weight = 1
tags = ["web apis"] 
+++

{{< tabs >}}
{{% tab name="index.html" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="./style.css" />
    <title>Coding Timetracker</title>
  </head>
  <body>
    <div class="wrapper">
      <h1>Coding Timetracker</h1>
      <h2><span id="counter">0</span> Hours Spent Coding Today</h2>
      <button id="add">Increment</button>
      <button id="subtract">Decrement</button>
    </div>
    <script src="./script.js"></script>
  </body>
</html>
```

{{% /tab %}}
{{% tab name="style.css" %}}
```css
*, *::before, *::after {
  box-sizing: border-box;
}

html {
  font-size: 16px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
  margin: 0;
  padding: 0;
  font-weight: normal;
}

.wrapper {
  width: 800px;
  margin: 0 auto;
  text-align: center;
}

h1 {
  font-size: 3em;
}

#add, #subtract {
  border-radius: 4px;
  border-style: none;
  box-shadow: rgba(34,36,38,.15) 0 0 0 0 inset;
  color: #fff;
  cursor: pointer;
  font-family: "Helvetica Neue",Arial,Helvetica,sans-serif;
  font-size: 1em;
  font-weight: 700;
  line-height: 0;
  padding: 20px;
}

#add {
  background-color: #2185d0;
}

#add:hover {
  background-color: #1678c2;
}

#subtract {
  background-color: #db2828;
}

#subtract:hover {
  background-color: #CF1919;
}

```
{{% /tab %}}
{{% tab name="script.js" %}}
```js
var counter = document.querySelector("#counter");
var addButton = document.querySelector("#add");
var subtractButton = document.querySelector("#subtract");

var count = localStorage.getItem("count");

counter.textContent = count;

addButton.addEventListener("click", function() {
  count++;
  counter.textContent = count;

  localStorage.setItem("count", count);
});

subtractButton.addEventListener("click", function() {
  count--;
  counter.textContent = count;

  localStorage.setItem("count", count);
});
```
{{% /tab %}}
{{< /tabs >}}

