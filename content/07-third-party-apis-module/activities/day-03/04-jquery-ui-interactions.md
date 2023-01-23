+++
title = "04. jQuery UI Interactions 👩‍🎓👨‍🎓"
weight = 4
tags = ["third party apis"] 
+++

# 📖 Implement a Sortable List with Drag and Drop

Implement the following user story:

* As a user, I want to be able to sort my list of skills using the cursor to drag and drop them.

## Acceptance Criteria

* It's done when the list of skills can be reorganized and sorted using drag-and-drop functionality.

* It's done when a placeholder is filling empty space.

## 📝 Notes

Refer to the following documentation:

[jQuery UI demos](https://jqueryui.com/demos/)

## 💡 Hint

* Think about which interaction will allow a user to drag an element to a new spot on the list.

## 🏆 Bonus

If you have completed the activity and want to further your knowledge, work through the following challenge:

* Can we implement drag-and-drop functionality without jQuery?

Use [Google](https://www.google.com) or another search engine to research this.

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

  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.0/css/bootstrap.min.css" />
  <link rel="stylesheet" href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css" />
  <link rel="stylesheet" href="./assets/css/style.css" />

  <title>jQuery UI Interactions</title>
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
            <label for="skill" class="col-sm-4 col-form-label">Skill Name:
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

// Sortable interaction
$(function () {
  $('#skills-list').sortable({
    placeholder: 'ui-state-highlight',
  });
  $('#skills-list').disableSelection();
});
```
{{% /expand%}}