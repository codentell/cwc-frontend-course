+++
title = "03. jQuery UI Interactions 👩‍🏫🧑‍🏫"
weight = 3
tags = ["third party apis"] 
+++

```html
<!DOCTYPE html>
<!-- Resulting code after Instructor Demo -->
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <!-- Changed title -->
    <title>jQuery UI Sortable</title>
    <link
      rel="stylesheet"
      href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css"
    />
    <!-- Imported our own custom stylesheet -->
    <link rel="stylesheet" href="./assets/css/style.css" />
  </head>
  <body>
    <!-- Added body content -->
    <h1>jQuery UI Interactions - Sortable</h1>
    <h2>What are you most excited to learn more about?</h2>
    <div>
      <ul id="sortable">
        <!-- Ask the class for skills and use them to populate this list -->
        <li class="ui-state-default">
          Node.js
        </li>
        <li class="ui-state-default">
          HTML
        </li>
        <li class="ui-state-default">
          MySQL
        </li>
        <li class="ui-state-default">
          Express.js
        </li>
        <li class="ui-state-default">
          NoSQL
        </li>
        <li class="ui-state-default">
          React
        </li>
        <li class="ui-state-default">
          JavaScript
        </li>
      </ul>
    </div>
  </body>
  <!-- Moved jQuery <script> tags -->
  <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
  <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
  <script>
    $(function () {
      $('#sortable').sortable();
      $('#sortable').disableSelection();
    });
  </script>
</html>

```

```html
<!DOCTYPE html>
<!-- From the jQuery UI Sortable Docs. To be used as starter code -->
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <!-- Change the title -->
    <title>jQuery UI Sortable - Default functionality</title>
    <link
      rel="stylesheet"
      href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css"
    />
    <!-- Change to our own custom stylesheet -->
    <link rel="stylesheet" href="/resources/demos/style.css" />
    <!-- Add this <style> code to the custom stylesheet -->
    <style>
      #sortable {
        list-style-type: none;
        margin: 0;
        padding: 0;
        width: 60%;
      }
      #sortable li {
        margin: 0 3px 3px 3px;
        padding: 0.4em;
        padding-left: 1.5em;
        font-size: 1.4em;
        height: 18px;
      }
      #sortable li span {
        position: absolute;
        margin-left: -1.3em;
      }
    </style>
    <!-- Move the jQuery <script> tags to the bottom -->
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script>
      $(function () {
        $('#sortable').sortable();
        $('#sortable').disableSelection();
      });
    </script>
  </head>
  <body>
    <!-- Change body content -->
    <ul id="sortable">
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 1
      </li>
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 2
      </li>
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 3
      </li>
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 4
      </li>
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 5
      </li>
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 6
      </li>
      <li class="ui-state-default">
        <span class="ui-icon ui-icon-arrowthick-2-n-s"></span>Item 7
      </li>
    </ul>
  </body>
  <!-- See index.html file for the resulting code -->
</html>

```