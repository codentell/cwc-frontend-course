+++
title = "06. Moment Format 👩‍🎓👨‍🎓"
weight = 6
tags = ["third party apis"] 
+++

# 📖 Create Solutions to the Date Quiz

Implement the following user story:

* As a user, I want to be able to view the correct answers to multiple questions about dates and time.

## Acceptance Criteria

* It's done when every question prompt on the page is correctly answered and displayed in the correct format using Moment.js.

## 📝 Notes

Refer to the following documentation:

[Moment.js Docs](https://momentjs.com/docs/#/displaying/)

**Note**: `Moment.js` has historically been the most popular date/time library, but is now no longer supported by its developers. It is still functional and widely used, which is why we are introducing it through this unit.

## 💡 Hints

* Refer to the official [Moment.js docs on parsing](https://momentjs.com/docs/#/parsing/) to format ISO 8601 strings.

* Follow the instructions provided by the comments in the starter code to format the date that answers the questions and assign them to the declared variable provided.

* Save often and check [index.html](starter/index.html) in your browser to see your progress.

## 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge:

* How can we measure the difference between two time stamps with `Moment.js`? Read the [Moment.js Docs](https://momentjs.com/docs/) to research how this works.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Moment Format</title>
    <link href="https://fonts.googleapis.com/css2?family=Nanum+Gothic&family=Varela+Round&display=swap" rel="stylesheet">
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
          1.  What is your graduation date in the following format: 1 Jan 1999?
          <p id="1a" class="answer"></p>
        </p>
        <p class="question">
          2. What day of the week will 1/1/2022 be? 
          <p id="2a" class="answer"></p>
        </p>
        <p class="question">
          3. Out of 365, what day of the year is today?(or 366 in a leap year)
          <p id="3a" class="answer"></p>
        </p>
        <p class="question">
          4. What is the current time in the following format, hours:minutes:seconds?
          <p id="4a" class="answer"></p>
        </p>
        <p class="question">
          5. What is the current Unix timestamp?
          <p id="5a" class="answer"></p>
        </p>
        <p class="question">
          6. Parse the following Unix timestamp, 1318781876, and convert into any time/date format.
          <p id="6a" class="answer"></p>
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
// TODO: 1. What is your graduation date in the following format: Jan 1st, 1999?
var gradDate = moment("2021-06-15").format("D MMM YYYY");
$("#1a").text(gradDate);

// TODO: 2. What day of the week will 1/1/2022 be?
var weekDay = moment("1.1.2022", "D.M.YYYY").format("ddd D MMM YYYY");
$("#2a").text(weekDay);

// TODO: 3. Out of 365, what day of the year is today?
var dayYear = moment().format("DDD");
$("#3a").text(dayYear);

// TODO: 4. What is the current time in the format: hours:minutes:seconds
var time = moment().format("HH:mm:ss");
$("#4a").text(time);

// TODO: 5. What is the current Unix timestamp?
var unix = moment().format("X");
$("#5a").text(unix);

// TODO: 6. Parse the following Unix timestamp, 1318781876, and convert into any time/date format.
var unixFormat = moment.unix(1318781876).format("D MMM YYYY, HH:mm:ss");
$("#6a").text(unixFormat);
```
{{% /expand%}}