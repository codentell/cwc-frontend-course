+++
title = "02. jQuery UI Widgets 👩‍🎓👨‍🎓"
weight = 2
tags = ["third party apis"] 
+++

# 📖 Enhance UI with jQuery UI Widgets

Work with a partner to implement the following user stories:

* As a user, I want to easily choose a skill from a list to use in the form.

* As a user, I want to easily select a date from a datepicker instead of writing it out manually.

## Acceptance Criteria

* It's done when the form input for entering a skill has an autocomplete feature added to it, to pick from a list of skills.

* It's done when the form input for entering a date has a datepicker feature added to it, to select by month and year.

## 📝 Notes

Refer to the following documentation: 

[jQuery UI Demos](https://jqueryui.com/demos/)

## 💡 Hints

* You will need to add an array of skills to use with the autocomplete widget (for example, `JavaScript`, `Node.js`, `Bootstrap`, `React`, and `CSS`). 

* Look for "Display month & year menus" in the list of examples on the datepicker widget page of the jQuery UI docs.

## 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge with your partner: 

* What built-in HTML feature can also help enforce a date? Use [Google](https://www.google.com) or another search engine to answer the preceding question.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.0/css/bootstrap.min.css"
    />
    <!-- jQuery UI <link> tag -->
    <link
      rel="stylesheet"
      href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css"
    />
    <link rel="stylesheet" href="./assets/css/style.css" />

    <title>jQuery UI Widgets</title>
  </head>
  <body>
    <div class="jumbotron jumbotron-fluid bg-info text-light">
      <div class="container text-center">
        <h1>
          Skills List
        </h1>
      </div>
    </div>
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-6">
          <h3>Skills Form</h3>
          <br />
          <form id="skills-form">
            <div class="form-group row">
              <label for="skill" class="col-sm-4 col-form-label"
                >Skill Name:
              </label>
              <div class="col-sm-8">
                <input type="text" class="form-control" id="skill-name" />
              </div>
            </div>
            <div class="form-group row">
              <label for="date" class="col-sm-4 col-form-label">Date: </label>
              <div class="col-sm-8">
                <input type="text" class="form-control" id="datepicker" autocomplete="off" />
              </div>
            </div>
            <button type="submit" value="Submit" class="btn btn-info">
              Submit
            </button>
          </form>
        </div>
        <div class="col-6">
          <h3>List of Skills:</h3>
          <br />
          <ul class="list-group" id="skills-list"></ul>
        </div>
      </div>
    </div>
  </body>

  <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
  <!-- jQuery UI <script> tag -->
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
  <script src="./assets/js/script.js"></script>
</html>
```
### script.js
```js
var formEl = $('#skills-form');
var nameInputEl = $('#skill-name');
var dateInputEl = $('#datepicker');
var skillsListEl = $('#skills-list');

var printSkills = function (name, date) {
  var listEl = $('<li>');
  var listDetail = name.concat(' on ', date);
  listEl.addClass('list-group-item').text(listDetail);
  listEl.appendTo(skillsListEl);
};

var handleFormSubmit = function (event) {
  event.preventDefault();

  var nameInput = nameInputEl.val();
  var dateInput = dateInputEl.val();

  if (!nameInput || !dateInput) {
    console.log('You need to fill out the form!');
    return;
  }

  printSkills(nameInput, dateInput);

  // resets form
  nameInputEl.val('');
  dateInputEl.val('');
};

formEl.on('submit', handleFormSubmit);

// Autocomplete widget
$(function () {
  var skillNames = [
    'Bootstrap',
    'C',
    'C++',
    'CSS',
    'Express.js',
    'Git',
    'HTML',
    'Java',
    'JavaScript',
    'jQuery',
    'JSON',
    'MySQL',
    'Node.js',
    'NoSQL',
    'PHP',
    'Python',
    'React',
    'Ruby',
  ];
  $('#skill-name').autocomplete({
    source: skillNames,
  });
});

// Datepicker widget
$(function () {
  $('#datepicker').datepicker({
    changeMonth: true,
    changeYear: true,
  });
});


```
{{% /expand%}}