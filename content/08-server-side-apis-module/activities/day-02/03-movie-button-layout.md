+++
title = "03. Movie Button Layout 👩‍🎓👨‍🎓"
weight = 3
tags = ["server side apis"] 
+++

# Movie Button Layout

## Instruction

* Using your previous activity files or the starter code provided, complete the following requirements.

* Your final code should:

  * Dynamically generate at least 4 buttons, using jQuery, above the search bar.

    * Each button should be a different movie title.

  * Allow users to create new buttons upon entering text in the textbox and clicking `Add a Movie`.

  * If you finish early, begin reading about [HTML5 `data-*` attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) and how (and why) you would add them to dynamically generated elements with the [jQuery `.attr()` method](http://api.jquery.com/attr/).

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

    <!-- Movies will get dumped here -->
    <div id="buttons-view"></div>

    <form id="movie-form">
      <label for="movie-input">Add a Movie
!</label>
      <input type="text" id="movie-input"><br>

      <!-- Button triggers new movie to be added -->
      <input id="add-movie" type="submit" value="Add a Movie
!">
    </form>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <script type="text/javascript" src="./script.js"></script>
  </div>
</body>

</html>
```

### script.js
```js
// Initial array of movies
var movies = ["The Matrix", "Dune", "Mr. Right", "The Lion King"];

// Function for displaying movie data
function renderButtons() {

  // Deleting the movie buttons prior to adding new movie buttons
  // (this is necessary otherwise we will have repeat buttons)
  $("#buttons-view").empty();

  // Looping through the array of movies
  for (var i = 0; i < movies.length; i++) {

    // Then dynamicaly generating buttons for each movie in the array.
    // This code $("<button>") is all jQuery needs to create the start and end tag. (<button></button>)
    var a = $("<button>");
    // Adding a class
    a.addClass("movie");
    // Adding a data-attribute with a value of the movie at index i
    a.attr("data-name", movies[i]);
    // Providing the button's text with a value of the movie at index i
    a.text(movies[i]);
    // Adding the button to the HTML
    $("#buttons-view").append(a);
  }
}

// This function handles events where one button is clicked
$("#add-movie").on("click", function(event) {
  // event.preventDefault() prevents the form from trying to submit itself.
  // We're using a form so that the user can hit enter instead of clicking the button if they want
  event.preventDefault();

  // This line will grab the text from the input box
  var movie = $("#movie-input").val().trim();
  // The movie from the textbox is then added to our array
  movies.push(movie);

  // calling renderButtons which handles the processing of our movie array
  renderButtons();
});

// Calling the renderButtons function at least once to display the initial list of movies
renderButtons();

```

{{% /expand%}}