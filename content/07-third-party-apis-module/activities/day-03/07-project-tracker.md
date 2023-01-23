+++
title = "07. Project Tracker 👩‍🎓👨‍🎓"
weight = 7
tags = ["third party apis"] 
+++

# Mini Project: Project Tracker

In this project, you will work with others to create a project tracker application using Bootstrap, jQuery, jQueryUI, Moment, and Google Fonts. Break up these phases amongst members of your team.

## Instructions

This mini-project is divided into four tasks. The first three tasks will get you to MVP, so focus on those first!

### Task 1: HTML Build

1. Create a header/hero area that welcomes users to the application and displays the current time and date using Moment.js with `setInterval()`.

2. Create a Bootstrap card component explaining the instructions of how to use the app and a button to open a [Bootstrap modal dialog](https://getbootstrap.com/docs/4.5/components/modal/).

3. The modal should contain a form asking users to fill in the following data:

    * The name of the project

    * The type of project (use a `<select>` drop-down)

    * The hourly wage for the project

    * The due date for the project (use jQuery UI's datepicker with a minimum date setting in place)

4. Include a Bootstrap table that the project's information can be printed to with columns for the following data:

    * Project name

    * Project type

    * Hourly wage

    * Due date

    * Days until the due date (use Moment.js to calculate)

    * Estimated total earned (hourly wage at 8 hours per day multiplied by the number of days until the due date)

While you build, remember the following guidelines:

  * Ensure that any elements you need to interact with using JavaScript/jQuery are properly identified (e.g., form elements, the table body, etc.).

  * Use different `<input>` element attributes to help enforce rules, like different `type` attribute values, minimum values, and required! See the [MDN web docs on the HTML input element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) for more guidance.

  * When in doubt, read the Bootstrap documentation.

---

### Task 2: Capture Form Data

1. Using jQuery, set up functionality to capture the form's input elements on submit and use that data to create a new table row on the page.

2. Select and save references to every DOM element we will interact with to a variable (i.e., `var projectFormEl = $("#project-form");`) so that we can use these elements later.

3. Attach a submit event listener to the `<form>` element using jQuery.

4. On submission, capture the four input values from the form and pass them to another function to handle printing project data. Having one function that captures the data and another that prints the data to the page's `<table>` element will improve code readability.

---

### Task 3: Print Project Data to Page

1. Create a function that will accept the four input fields' data as arguments.

2. Create a table row (`<tr>`) element and save it to a variable.

3. Create a table detail (`<td>`) element for each of the table columns created in Task 1.

4. For printing the days to the due date, use Moment.js to calculate the difference between the due date and the current time in days. 

5. For printing the estimated total earned amount, assume that you work an eight-hour day. So multiply the hourly rate by 8 to get the daily rate, then multiply that value by how many days until the project is due to get the estimated total earned. 

6. Append all `<td>` elements to the table row created, then append the entire row to the `<tbody>` element on the page.

7. Don't forget to close the modal when done!

---

### Task 4: Delete a Project From the Table

1. Update the table to accommodate one more column without a name.

2. When generating a new `<tr>` for a project, add one more `<td>` that holds a button for deleting a project from the list.

3. Use jQuery event delegation to attach an event listener to each of those buttons so that when clicked, the parent `<tr>` element will be removed from the page.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <meta name="Description" content="Enter your description here" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.0/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">

  <link href="https://fonts.googleapis.com/css2?family=Fira+Sans:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="./assets/css/style.css">
  <title>Project Tracker</title>
</head>

<body>

  <header class="jumbotron jumbotron-fluid custom-jumbotron">
    <div class="container text-center">
      <h1>Project Tracker</h1>
      <h2>Current Time &amp; Date: <br /> <span id="time-display">00:00:00</span></h2>
    </div>
  </header>

  <main class="container-fluid">
    <div class="row">
      <section class="col-12 col-md-4 col-lg-3">
        <div class="card custom-card">
          <h3 class="card-header">
            Instructions
          </h3>
          <div class="card-body">
            <div class="card-text">
              Click the button below to open a form and provide information for the following:
            </div>
          </div>
          <ul class="list-group list-group-flush">
            <li class="list-group-item">Project Name</li>
            <li class="list-group-item">Project Type</li>
            <li class="list-group-item">Due Date</li>
            <li class="list-group-item">Hourly Rate</li>
          </ul>
          <div class="card-footer">
            <button class="btn btn-block custom-btn" data-toggle="modal" data-target="#project-modal">Add
              Project</button>
          </div>
        </div>
      </section>

      <section class="col-12 col-md-8 col-lg-9">
        <div class="table-responsive">
          <table class="table table-bordered custom-table">
            <thead>
              <tr>
                <th scope="col">Project Name</th>
                <th scope="col">Project Type</th>
                <th scope="col">Hourly Rate ($)</th>
                <th scope="col">Due Date</th>
                <th scope="col">Days Until Due Date</th>
                <th scope="col">Potential Total Earnings ($)</th>
                <th scope="col" class="p-3"></th>
              </tr>
            </thead>
            <tbody id="project-display"></tbody>
          </table>
        </div>
      </section>
    </div>
  </main>

  <!-- Modal -->
  <div class="modal fade custom-modal" id="project-modal" tabindex="-1" role="dialog"
    aria-labelledby="project-modal-form" aria-hidden="true">
    <div class="modal-dialog modal-lg modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="project-modal-form">Add a new project.</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <form id="project-form">
          <div class="modal-body">
            <div class="form-group">
              <label for="project-name-input">Project Name</label>
              <input type="text" id="project-name-input" class="form-control" placeholder="Enter the project's name"
                required />
            </div>

            <div class="form-group">
              <label for="project-type-input">Project Type</label>
              <select class="form-control" id="project-type-input">
                <option selected disabled>Pick one...</option>
                <option value="Web Application (Front End)">Web Application (Front End)</option>
                <option value="Web Application (Back End)">Web Application (Back End)</option>
                <option value="Web Application (Full Stack)">Web Application (Full Stack)</option>
                <option value="Mobile Application">Mobile Application</option>
                <option value="Print Campaign">Print Campaign</option>
                <option value="Digital Marketing Campaign">Digital Marketing Campaign</option>
              </select>
            </div>

            <div class="form-group">
              <label for="hourly-rate-input">Hourly Rate ($)</label>
              <input type="number" id="hourly-rate-input" class="form-control" placeholder="$" min="0" required />
            </div>

            <div class="form-group">
              <label for="due-date-input">Due Date</label>
              <input type="text" min='1' id="due-date-input" class="form-control" placeholder="When is the project due?"
                required />
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="submit" class="btn custom-btn">Submit Project Info</button>
          </div>
        </form>
      </div>
    </div>
  </div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.1/umd/popper.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.0/js/bootstrap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.27.0/moment.min.js"></script>
  <script src="https://code.jquery.com/ui/1.12.0/jquery-ui.min.js"></script>
  <script src="./assets/js/script.js"></script>
</body>

</html>
```
### script.js
```js
// save reference to important DOM elements
var timeDisplayEl = $('#time-display');
var projectDisplayEl = $('#project-display');
var projectModalEl = $('#project-modal');
var projectFormEl = $('#project-form');
var projectNameInputEl = $('#project-name-input');
var projectTypeInputEl = $('#project-type-input');
var hourlyRateInputEl = $('#hourly-rate-input');
var dueDateInputEl = $('#due-date-input');

// handle displaying the time
function displayTime() {
  var rightNow = moment().format('DD MMM YYYY [at] hh:mm:ss a');
  timeDisplayEl.text(rightNow);
}

// handle printing project data to the page
function printProjectData(name, type, hourlyRate, dueDate) {
  var projectRowEl = $('<tr>');

  var projectNameTdEl = $('<td>').addClass('p-2').text(name);

  var projectTypeTdEl = $('<td>').addClass('p-2').text(type);

  var rateTdEl = $('<td>').addClass('p-2').text(hourlyRate);

  var dueDateTdEl = $('<td>').addClass('p-2').text(dueDate);

  var daysToDate = moment(dueDate, 'DD/MM/YY').diff(moment(), 'days');
  var daysLeftTdEl = $('<td>').addClass('p-2').text(daysToDate);

  var totalEarnings = calculateTotalEarnings(hourlyRate, daysToDate);

  // You can also chain methods onto new lines to keep code clean
  var totalTdEl = $('<td>')
    .addClass('p-2')
    .text('$' + totalEarnings);

  var deleteProjectBtn = $('<td>')
    .addClass('p-2 delete-project-btn text-center')
    .text('X');

  // By listing each `<td>` variable as an argument, each one will be appended in that order
  projectRowEl.append(
    projectNameTdEl,
    projectTypeTdEl,
    rateTdEl,
    dueDateTdEl,
    daysLeftTdEl,
    totalTdEl,
    deleteProjectBtn
  );

  projectDisplayEl.append(projectRowEl);

  projectModalEl.modal('hide');
}

function calculateTotalEarnings(rate, days) {
  var dailyTotal = rate * 8;
  var total = dailyTotal * days;
  return total;
}

function handleDeleteProject(event) {
  console.log(event.target);
  var btnClicked = $(event.target);
  btnClicked.parent('tr').remove();
}

// handle project form submission
function handleProjectFormSubmit(event) {
  event.preventDefault();

  var projectName = projectNameInputEl.val().trim();
  var projectType = projectTypeInputEl.val().trim();
  var hourlyRate = hourlyRateInputEl.val().trim();
  var dueDate = dueDateInputEl.val().trim();

  printProjectData(projectName, projectType, hourlyRate, dueDate);

  projectFormEl[0].reset();
}

projectFormEl.on('submit', handleProjectFormSubmit);
projectDisplayEl.on('click', '.delete-project-btn', handleDeleteProject);
dueDateInputEl.datepicker({ minDate: 1 });

setInterval(displayTime, 1000);
```
{{% /expand%}}