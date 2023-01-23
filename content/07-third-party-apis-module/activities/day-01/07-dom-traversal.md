+++
title = "07. Dom Traversal 👩‍🏫🧑‍🏫"
weight = 7
tags = ["third party apis"] 
+++


{{< tabs >}}
{{% tab name="index.html" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8" />
  <title>Traversing the DOM</title>
  <link rel="stylesheet" type="text/css" href="./assets/css/jass.css">
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
</head>

<body class="bg-dark text-light">
  <main id="top">
    <h1>Developer Community Center</h1>
    <p>The world's leading source on <strong>open-sources</strong> related to web </p>
    <hr /> 
    <h2>Types of Resources</h2>
    <ul>
      <li>Stack Overflow</li>
      <li>Twitter</li>
      <li>Reddit</li>
      <li>GitHub</li>
    </ul>
  </main>
  
  <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script> 

  <script type="text/javascript" src="./assets/js/script.js"></script>
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

ul {
  list-style-type: none;
  padding: 0;
}

.boxy {
  color: red;
  border: #48b4ef 2px solid;
  text-align: center;
  border-radius: .4rem;
}

.bg-primary {
  background-color: #48b4ef;
}
```
{{% /tab %}}

{{% tab name="index.js" %}}
```js
// Highlight which elements in the DOM are the children of the parent element
// Uncomment the following two lines to see the which elements are the children to the #top
// $('#top').children().css('color', 'yellow');
// console.log($('#top').children());

// Uncomment the following line to see the which element is the first direct child of the <main>
// $('#top').children().eq(0).addClass('boxy');

// Uncomment the following line to add a list item to the list
// $('#top').children().eq(4).append($('<li>Classmates</li>'));

// Uncomment the following line to style the list items
// $('#top').children('ul').children().addClass('bg-primary text-dark mb-3 p-3').css('border-radius', '.4rem');

```
{{% /tab %}}
{{< /tabs >}}



