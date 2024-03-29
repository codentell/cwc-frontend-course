+++
title = "04. Click JSON 👩‍🎓👨‍🎓"
weight = 4
tags = ["server side apis"] 
+++


# Click JSON Printing

## Instructions

* Using your previous activity files or the starter code provided complete the following:
 
  * Create a function called `displayMovieInfo` that when called prints JSON data for the appropriate movie.

    * This function should be called when a Movie button is clicked.

## 💡 Hint 

Make sure you utilize data-attributes.

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
  <style type="text/css">
    button,
    div,
    form,
    input {
      margin: 10px;
    }
  </style>
</head>

<body>

  <div class="container">
    <h1>Movie Search</h1>

    <!-- Rendered Buttons will get Dumped Here  -->
    <div id="buttons-view"></div>

    <form id="movie-form">
      <label for="movie-input">Add a Movie
!</label>
      <input type="text" id="movie-input"><br>

      <!-- Button triggers new movie to be added -->
      <input id="add-movie" type="submit" value="Add a Movie
!">
    </form>

    <!-- Movies will Get Dumped Here -->
    <div id="movies-view"></div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script type="text/javascript" src="./script.js">
      
    </script>
  </div>
</body>

</html>
```
### script.js
```js
// Initial array of movies
var movies = ["The Matrix", "Dune", "Mr. Right", "The Lion King"];

// Function for dumping the JSON content for each button into the div
function displayMovieInfo() {

  var movie = $(this).attr("data-name");
  var queryURL = "https://www.omdbapi.com/?t=" + movie + "&apikey=trilogy";

  $.ajax({
    url: queryURL,
    method: "GET"
  }).then(function(response) {
    $("#movies-view").text(JSON.stringify(response));
  });
}

// Function for displaying movie data
function renderButtons() {

  // Deleting the buttons prior to adding new movies
  // (this is necessary otherwise you will have repeat buttons)
  $("#buttons-view").empty();

  // Looping through the array of movies
  for (var i = 0; i < movies.length; i++) {

    // Then dynamically generating buttons for each movie in the array
    // This code $("<button>") is all jQuery needs to create the beginning and end tag. (<button></button>)
    var a = $("<button>");
    // Adding a class of movie to our button
    a.addClass("movie");
    // Adding a data-attribute
    a.attr("data-name", movies[i]);
    // Providing the initial button text
    a.text(movies[i]);
    // Adding the button to the buttons-view div
    $("#buttons-view").append(a);
  }
}

// This function handles events where one button is clicked
$("#add-movie").on("click", function(event) {
  event.preventDefault();

  // This line grabs the input from the textbox
  var movie = $("#movie-input").val().trim();

  // Adding the movie from the textbox to our array
  movies.push(movie);
  console.log(movies);

  // Calling renderButtons which handles the processing of our movie array
  renderButtons();
});

// Function for displaying the movie info
// Using $(document).on instead of $(".movie").on to add event listeners to dynamically generated elements
$(document).on("click", ".movie", displayMovieInfo);

// Calling the renderButtons function to display the initial buttons
renderButtons();
```
{{% /expand%}}