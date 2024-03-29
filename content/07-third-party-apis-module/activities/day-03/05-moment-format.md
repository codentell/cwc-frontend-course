+++
title = "05. Moment Format 👩‍🏫🧑‍🏫"
weight = 5
tags = ["third party apis"] 
+++

### index.html

```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Moment Functions</title>
    <link
      href="https://fonts.googleapis.com/css2?family=Krona+One&family=Pacifico&family=Roboto:wght@700&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="./assets/css/style.css" />
    <script
      type="text/javascript"
      src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.27.0/moment.min.js"
    ></script>
    <script
      src="https://code.jquery.com/jquery-3.5.1.min.js"
      integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
      crossorigin="anonymous"
    ></script>
  </head>
  <body>
    <main>
      <section class="jumbotron">
        <h1 class="title">Moment Quiz</h1>
        <p>Answer the following questions</p>
      </section>
      <section>
        <p class="question">
          1. What is today's date in the following format: 1 Jan 1999?
          <p id="1a" class="answer"></p>
        </p>
        <p class="question">
          2. What is the day of the week today?
          <p id="2a" class="answer"></p>
        </p>
        <p class="question">
          3. Parse the following date, 3/11/2020, and convert it into the following format: Sunday, 14 February 2010, 3:25:50 pm.
          <p id="3a" class="answer"></p>
        </p>
        <p class="question">
          4. I need to place my recycling bin on the curb on every odd week of the year for collection. Do I need to put out my recycling bin out this week?
          <p id="4a" class="answer"></p>
        </p>
      </section>
    </main>
    <script src="./assets/js/script.js"></script>
  </body>
</html>
```

### script.js
```js
// Use Moment.js to format the following variables:
// 1. What is today's date in the following format: Jan 1st, 1999?
var today = moment();
$("#1a").text(today.format("D MMM YYYY"));

// 2. What is the day of the week today?
var dayWeek = today.format("[Today is] dddd")
$("#2a").text(dayWeek);

// 3. Parse the following date, 11/3/2020, and convert it into the following format: Sunday, February 14th 2010, 3:25:50 pm.
var reformatDate = moment("3/11/20", "DD-MM-YY").format("dddd, D MMMM YYYY, h:mm:ss a");
$("#3a").text(reformatDate);

// 4. I need to place my recycling bin on the curb on every odd week of the year for collection. Do I need to put out my recycling bin out this week?
var weekNum = today.format("w");
var takeOut;
// Check odd, then assign boolean
if(weekNum % 2) {
  takeOut = true;
} else {
  takeOut = false;
}

$("#4a").text(takeOut + ", because it's currently week " + weekNum);
```