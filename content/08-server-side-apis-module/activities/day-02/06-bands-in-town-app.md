+++
title = "06. Bands in Town App 👩‍🎓👨‍🎓"
weight = 6
tags = ["server side apis"] 
+++

# Bandsintown App

## Instructions

* Using the starter code provided to you, complete the application as follows:
 
  * Search the Bandsintown API for the artist specified in the search box.
  
  * Print the following information to the `#artist-div` as semantic HTML elements:

    * The artist's name
     
    * The artist's thumbnail image
     
    * The number of fans tracking this artist
     
    * The number of upcoming events for this artist
  
    * A link to the bandsintown url for this artist


## 📝 Notes

* Bandsintown is a service for finding out when and where bands and artists are scheduled to tour.

* Information on how to use query the Bandsintown API can be found [here](https://app.swaggerhub.com/apis/Bandsintown/PublicAPI/3.0.0).
  
* This is a free public API, and you will not need to sign up for anything.

## 💡 Hints

* Scroll down the API docs and study the examples. See if you can figure out how to query for an artist's information. You will need to use the `/artists/{artistname} endpoint`.

* The `app_id` parameter described in the docs is required but can be set to anything you wish.

---



## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### index.html

```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="utf-8">
  <title>Bands In Town</title>
</head>

<body>

  <!-- Artist Select Box -->
  <form id="artist-form">

    <!-- Label for Text Box -->
    <label for="artist-input">Choose Your Artist</label>

    <!-- Text Input Box -->
    <input type="text" id="artist-input"><br>

    <!-- Submit Button -->
    <input id="select-artist" type="submit" value="GO!">
  </form>

  <!-- Artist Information -->
  <div id="artist-div"></div>

</body>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script type="text/javascript" src="./script.js"></script>

</html>

```

### script.js
```js
function searchBandsInTown(artist) {

  // Querying the bandsintown api for the selected artist, the ?app_id parameter is required, but can equal anything
  var queryURL = "https://rest.bandsintown.com/artists/" + artist + "?app_id=codingbootcamp";
  $.ajax({
    url: queryURL,
    method: "GET"
  }).then(function(response) {

    // Printing the entire object to console
    console.log(response);

    // Constructing HTML containing the artist information
    var artistName = $("<h1>").text(response.name);
    var artistURL = $("<a>").attr("href", response.url).append(artistName);
    var artistImage = $("<img>").attr("src", response.thumb_url);
    var trackerCount = $("<h2>").text(response.tracker_count + " fans tracking this artist");
    var upcomingEvents = $("<h2>").text(response.upcoming_event_count + " upcoming events");
    var goToArtist = $("<a>").attr("href", response.url).text("See Tour Dates");

    // Empty the contents of the artist-div, append the new artist content
    $("#artist-div").empty();
    $("#artist-div").append(artistURL, artistImage, trackerCount, upcomingEvents, goToArtist);
  });
}

// Event handler for user clicking the select-artist button
$("#select-artist").on("click", function(event) {
  // Preventing the button from trying to submit the form
  event.preventDefault();
  // Storing the artist name
  var inputArtist = $("#artist-input").val().trim();

  // Running the searchBandsInTown function(passing in the artist as an argument)
  searchBandsInTown(inputArtist);
});
```

{{% /expand%}}