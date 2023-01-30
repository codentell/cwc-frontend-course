+++
title = "02. Movie JSON Dump 👩‍🎓👨‍🎓"
weight = 2
tags = ["server side apis"] 
+++


# Movie JSON Dump

## Instructions

* Using the provided starter code, add functionality such that clicking `Movie Search` triggers an AJAX call to the OMDb database and the JSON response to be appended onto the page.

## 💡 Hint 

You will need to use [JSON.stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) to render the AJAX response as text. 

* If you finish early, begin reading about the [Bandsintown API](https://app.swaggerhub.com/apis/Bandsintown/PublicAPI/3.0.0). Try to understand how to search for a specific artist.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="utf-8">
  <title>Favorite Movies</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.0.0/css/bootstrap.min.css" />
</head>

<body>
  <div class="container">
    <h1>Movie Search</h1>

    <!-- This form will be where users input data about the movies -->
    <form id="movie-form">
      <label for="movie-input">Search for a movie</label>
      <input type="text" id="movie-input"><br>

      <!-- This button will trigger our AJAX call -->
      <input id="find-movie" type="submit" value="Movie Search">
    </form>

    <!-- We'll be dumping our JSON contents in here -->
    <div id="movie-view"></div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script type="text/javascript" src="./script.js"></script>
  </div>
</body>

</html>
```

### script.js
```js
// This .on("click") function will trigger the AJAX Call
$("#find-movie").on("click", function(event) {

  // event.preventDefault() can be used to prevent an event's default behavior.
  // Here, it prevents the submit button from trying to submit a form when clicked
  event.preventDefault();

  // Here we grab the text from the input box
  var movie = $("#movie-input").val();

  // Here we construct our URL
  var queryURL = "https://www.omdbapi.com/?t=" + movie + "&apikey=trilogy";

  // Write code between the dashes below to hit the queryURL with $ajax, then take the response data
  // and display it in the div with an id of movie-view

  // ------YOUR CODE GOES IN THESE DASHES.

  $.ajax({
    url: queryURL,
    method: "GET"
  }).then(function(response) {
    $("#movie-view").text(JSON.stringify(response));
  });

  // -----------------------------------------------------------------------

});
```
{{% /expand%}}
