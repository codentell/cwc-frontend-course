+++
title = "09. Event Delegation 👩‍🏫🧑‍🏫"
weight = 9
tags = ["third party apis"] 
+++


{{< tabs >}}
{{% tab name="index.html" %}}
```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Message Board</title>
  <link rel="stylesheet" type="text/css" href="./assets/css/jass.css">
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
</head>

<body class="bg-dark text-light">
  <main>
    <h1>Write your message.</h1>
    <hr/>
    <!-- Message board -->
    <div id="display" class="my-5 bg-light text-dark p-5"></div>
    <!-- Show Letters button -->
    <button class="btn btn-lg" id="show-letters-btn">Show Letters</button>
    <!-- Alphabet letter buttons -->
    <div id="buttons" class="my-5"></div>
    <!-- Clear button -->
    <button id="clear" class="btn btn-block d-block btn-danger">Clear</button>
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

.letter {
  width: 30px;
  height: 30px;
  border-style: solid;
  padding: 2px;
  margin: 2px;
  display: inline-block;
}

.letter-button {
  margin: 0.25rem;
  font-size: 1.25rem;
}
```
{{% /tab %}}

{{% tab name="index.js" %}}
```js
var displayEl = $('#display');
var showLettersBtnEl = $('#show-letters-btn');
var buttonListEl = $('#buttons');
var clearEl = $('#clear');

// Immediately hide the clear button
clearEl.hide();

function renderLetters() {
  var letters = [
    'A',
    'B',
    'C',
    'D',
    'E',
    'F',
    'G',
    'H',
    'I',
    'J',
    'K',
    'L',
    'M',
    'N',
    'O',
    'P',
    'Q',
    'R',
    'S',
    'T',
    'U',
    'V',
    'W',
    'X',
    'Y',
    'Z',
    '_',
  ];

  // Dynamically create buttons
  // Create a for-loop to iterate through the letters array.
  for (var i = 0; i < letters.length; i++) {
    // Create button
    var letterBtn = $('<button>');
    // Assign style to the button
    letterBtn.addClass('letter-button btn btn-info');
    // Assign the letter to the data-letter attribute
    letterBtn.attr('data-letter', letters[i]);
    // Display the letter
    letterBtn.text(letters[i]);
    // Attach the letter element
    buttonListEl.append(letterBtn);
  }
}

// Delegate event listener to the parent element, <div id="buttons">
buttonListEl.on('click', '.letter-button', function (event) {
  var displayLetterEl = $('<div>');

  displayLetterEl.addClass('letter');

  // get letter from clicked letter button's `data-letter` attribute and use it for display
  displayLetterEl.text($(event.target).attr('data-letter'));
  displayEl.append(displayLetterEl);
});

// Renders the letter buttons on click
showLettersBtnEl.on('click', function () {
  // render letters
  renderLetters();
  // hide show letters button
  showLettersBtnEl.hide();
  // display clear button
  clearEl.show();
});

// Clears the message board of letters on click
clearEl.on('click', function () {
  displayEl.empty();
});
```
{{% /tab %}}
{{< /tabs >}}



