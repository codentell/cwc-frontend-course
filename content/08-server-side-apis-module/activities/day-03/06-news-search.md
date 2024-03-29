+++
title = "06. News Search 👩‍🎓👨‍🎓"
weight = 6
tags = ["server side apis"] 
+++

### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="UTF-8">
  <title>New York Times Search</title>
  <!-- Bootstrap CSS CDN  -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.0.0/css/bootstrap.min.css" />

  <!-- Font Awesome CSS Icons (For cool glyphicons) -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css" />

  <!-- Style to fix the issue of text extending past card length -->
  <style>
    .card-body a {
      word-break: break-all;
    }

    .articleHeadline {
      line-height: 1.5;
    }
  </style>
</head>

<body>

  <!-- Main Bootstrap Search -->
  <div class="container">

    <!-- Jumbotron for Title -->
    <div class="jumbotron" style="background-color: #20315A ; color: white;">
      <h1 class="text-center">
        <strong>
          <i class="fa fa-newspaper-o"></i> New York Times Search</strong>
      </h1>
    </div>

    <!-- Row for Searching New York Times -->
    <div class="row">
      <div class="col-sm-12">
        <br>
        <!-- First card is for handling the search parameters -->
        <div class="card">
          <div class="card-header">
            <strong>
              <i class="fa fa-list-alt"></i> Search Parameters</strong>
          </div>
          <div class="card-body">

            <!-- Here we create an HTML Form for handling the inputs-->
            <form role="form">

              <!-- Here we create the text box for capturing the search term-->
              <div class="form-group">
                <label for="search">Search Term:</label>
                <input type="text" class="form-control" id="search-term">
              </div>

              <!-- Here we capture the number of records that the user wants to retrieve  -->
              <div class="form-group">
                <label for="pwd">Number of Records to Retrieve:</label>
                <select id="article-count" class="custom-select" aria-labelledby="dropdownMenuButton">
                  <option selected value="1">1</option>
                  <!-- Setting the option for 5 as default -->
                  <option value="5" selected>5</option>
                  <option value="10">10</option>
                </select>
              </div>

              <!-- Here we capture the Start Year Parameter-->
              <div class="form-group">
                <label for="start-year">Start Year (Optional):</label>
                <input type="text" class="form-control" id="start-year">
              </div>

              <!-- Here we capture the End Year Parameter -->
              <div class="form-group">
                <label for="end-year">End Year (Optional):</label>
                <input type="text" class="form-control" id="end-year">
              </div>

              <!-- Here we have our final submit button -->
              <button type="submit" class="btn btn-default" id="run-search">
                <i class="fa fa-search"></i> Search</button>
              <button class="btn btn-default" id="clear-all">
                <i class="fa fa-trash"></i> Clear Results</button>

            </form>
          </div>
        </div>
      </div>
    </div>

    <!-- This row will handle all of the retrieved articles -->
    <div class="row">
      <div class="col-sm-12">
        <br>

        <!-- This card will initially be made up of a card and wells for each of the articles retrieved -->
        <div class="card">

          <!-- card Heading for the retrieved articles box -->
          <div class="card-header">
            <strong>
              <i class="fa fa-table"></i> Top Articles</strong>
          </div>

          <!-- This main card will hold each of the resulting articles -->
          <div class="card-body" id="article-section">
          </div>
        </div>
      </div>
    </div>

    <!-- Footer Region -->
    <div class="row">
      <div class="col-sm-12">

        <!-- Line Break followed by closing -->
        <hr>
        <h5 class="text-center">
          <small>Made with lots and lots of
            <i class="fa fa-heart"></i>
          </small>
        </h5>

      </div>
    </div>

  </div>

  <!-- jQuery JS -->
  <script src="https://code.jquery.com/jquery.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.0.0/js/bootstrap.bundle.min.js"></script>
  <!-- Code to the JavaScript File -->
  <script src="script.js"></script>

</body>

</html>

```

### script.js
```js
/**
 * pulls information from the form and build the query URL
 * @returns {string} URL for NYT API based on form inputs
 */
 function buildQueryURL() {
  // queryURL is the url we'll use to query the API
  var queryURL = "https://api.nytimes.com/svc/search/v2/articlesearch.json?";

  // Begin building an object to contain our API call's query parameters
  // Set the API key
  var queryParams = { "api-key": "R1a31F4tBjCUaM2ho8GtIFsrSdtXt30M" };

  // Grab text the user typed into the search input, add to the queryParams object
  queryParams.q = $("#search-term")
    .val()
    .trim();

  // If the user provides a startYear, include it in the queryParams object
  var startYear = $("#start-year")
    .val()
    .trim();

  if (parseInt(startYear)) {
    queryParams.begin_date = startYear + "0101";
  }

  // If the user provides an endYear, include it in the queryParams object
  var endYear = $("#end-year")
    .val()
    .trim();

  if (parseInt(endYear)) {
    queryParams.end_date = endYear + "0101";
  }

  // Logging the URL so we have access to it for troubleshooting
  console.log("---------------\nURL: " + queryURL + "\n---------------");
  console.log(queryURL + $.param(queryParams));
  return queryURL + $.param(queryParams);
}

/**
 * takes API data (JSON/object) and turns it into elements on the page
 * @param {object} NYTData - object containing NYT API data
 */
function updatePage(NYTData) {
  // Get from the form the number of results to display
  // API doesn't have a "limit" parameter, so we have to do this ourselves
  var numArticles = $("#article-count").val();

  // Log the NYTData to console, where it will show up as an object
  console.log(NYTData);
  console.log("------------------------------------");

  // Loop through and build elements for the defined number of articles
  for (var i = 0; i < numArticles; i++) {
    // Get specific article info for current index
    var article = NYTData.response.docs[i];

    // Increase the articleCount (track article # - starting at 1)
    var articleCount = i + 1;

    // Create the  list group to contain the articles and add the article content for each
    var $articleList = $("<ul>");
    $articleList.addClass("list-group");

    // Add the newly created element to the DOM
    $("#article-section").append($articleList);

    // If the article has a headline, log and append to $articleList
    var headline = article.headline;
    var $articleListItem = $("<li class='list-group-item articleHeadline'>");

    if (headline && headline.main) {
      console.log(headline.main);
      $articleListItem.append(
        "<span class='label label-primary'>" +
          articleCount +
          "</span>" +
          "<h2> " +
          headline.main +
          "</h2>"
      );
    }

    // If the article has a byline, log and append to $articleList
    var byline = article.byline;

    if (byline && byline.original) {
      console.log(byline.original);
      $articleListItem.append("<h3>" + byline.original + "</h3>");
    }

    // Log section, and append to document if exists
    var section = article.section_name;
    console.log(article.section_name);
    if (section) {
      $articleListItem.append("<h5>Section: " + section + "</h5>");
    }

    // Log published date, and append to document if exists
    var pubDate = article.pub_date;
    console.log(article.pub_date);
    if (pubDate) {
      $articleListItem.append("<h5>" + article.pub_date + "</h5>");
    }

    // Append and log url
    $articleListItem.append("<a href='" + article.web_url + "'>" + article.web_url + "</a>");
    console.log(article.web_url);

    // Append the article
    $articleList.append($articleListItem);
  }
}

// Function to empty out the articles
function clear() {
  $("#article-section").empty();
}

// CLICK HANDLERS
// ==========================================================

// .on("click") function associated with the Search Button
$("#run-search").on("click", function(event) {
  // This line allows us to take advantage of the HTML "submit" property
  // This way we can hit enter on the keyboard and it registers the search
  // (in addition to clicks). Prevents the page from reloading on form submit.
  event.preventDefault();

  // Empty the region associated with the articles
  clear();

  // Build the query URL for the ajax request to the NYT API
  var queryURL = buildQueryURL();

  // Make the AJAX request to the API - GETs the JSON data at the queryURL.
  // The data then gets passed as an argument to the updatePage function
  $.ajax({
    url: queryURL,
    method: "GET"
  }).then(updatePage);
});

//  .on("click") function associated with the clear button
$("#clear-all").on("click", clear);
```