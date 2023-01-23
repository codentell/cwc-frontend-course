+++
title = "03. Ajax Omdb 👩‍🏫🧑‍🏫"
weight = 3
tags = ["server side apis"] 
+++

### multiple 
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <title>Multiple AJAX</title>
</head>

<body>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript">
    // Performing GET requests to the OMDB API and logging the responses to the console
    $.ajax({
      url: "https://www.omdbapi.com/?t=romancing+the+stone&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });

    $.ajax({
      url: "https://www.omdbapi.com/?t=the+revenant&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });

    $.ajax({
      url: "https://www.omdbapi.com/?t=god+father&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });

    $.ajax({
      url: "https://www.omdbapi.com/?t=space+jam&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });

    $.ajax({
      url: "https://www.omdbapi.com/?t=boiler+room&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });

    $.ajax({
      url: "https://www.omdbapi.com/?t=inception&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });

    $.ajax({
      url: "https://www.omdbapi.com/?t=the+dark+night&y=&plot=short&apikey=trilogy",
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });
// ---------------------------------------------------------

    console.log("Because our AJAX requests are asynchronous, this line of code will most likely log first");
  </script>

</body>

</html>
```

### single
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <title>Single AJAX</title>
</head>

<body>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript">
    // constructing a queryURL variable we will use instead of the literal string inside of the ajax method
    var title = "Dune";
    var queryURL = "https://www.omdbapi.com/?t=" + title + "&y=&plot=short&apikey=trilogy";

    $.ajax({
      url: queryURL,
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });
// ---------------------------------------------------------

    console.log("This console.log will probably happen first because of asynchronicity.");
    var x = 2;
    var y = 10;
    var z = 13;
    console.log("We can also assign some variables and do some arithmetic while we wait too: 2 + 10 + 13 = ", x + y + z);
  </script>

</body>

</html>
```