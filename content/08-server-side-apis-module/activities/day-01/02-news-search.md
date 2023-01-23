+++
title = "02. News Search 👩‍🏫🧑‍🏫"
weight = 2
tags = ["server side apis"] 
+++

### index.html

```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
    <meta charset="UTF-8">
    <title>News Search</title>
    <!-- Added link to the jQuery Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
    <!-- Added a link to Bootstrap-->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7"
        crossorigin="anonymous">
    <link rel="stylesheet" type="text/css" href="assets/css/style.css">
</head>

<body>
    <div class="container">
        <!-- Jumbotron for Title -->
        <div class="jumbotron">
            <h1 id="message" class="text-center">News Search</h1>
            <h2 class="text-center">
        </div>
            <div class="search-container">
                <div class="panel panel-primary">
                    <div class="panel-heading">
                        <span class="glyphicon glyphicon-search"></span> Search Parameters</div>
                    <div class="panel-body">
                        <form>
                            <div class=“form-group”>
                                <div class="row">Search Term:
                                    <br>
                                    <div class="input-group col-md-12">
                                        <input type="text" class="form-control" aria-describedby="sizing-addon2" id="search-string">
                                    </div>
                                </div>
                                <br>
                                <button type="button" class="btn btn-default search">
                                    <span class="glyphicon glyphicon-search"></span> Search
                                </button>
                                <button type="button" class="btn btn-default clear">
                                    <span class="glyphicon glyphicon-trash"></span> Clear Results
                                </button>
                        </form>
                        </div>
                    </div>
                </div>
            </div>
            <div class="articles-container">
                <div class="panel panel-primary">
                    <div class="panel-heading">
                        <span class="glyphicon glyphicon-th"></span>Top Articles</div>
                    <div class="panel-body" id="article-results">
                    </div>
                </div>
            </div>
        <script type="text/javascript" src="assets/javascript/app.js"></script>
</body>

</html>
```

### app.js
```js
$(document).ready(function () {

    var apiURL = "https://gnews.io/api/v4/search?";
    var key = "&country=us&max=10&token=d06b56befd778f95afde57c26ebc9890";
    var searchString = "";
    var queryURL;
    var articleNumber = 0;
        
    
    $(".clear").click(function () {
        articleNumber = 0;
        $("#search-string").val("");
        $("#article-results").empty();
    });
    
    $(".search").on("click", function () {
        $("#article-results").empty();
        articleNumber = 0;
        searchString = $("#search-string").val();
        queryURL = apiURL + "q=" + searchString + key;
        console.log('query: ', queryURL)
        $.ajax({
            url: queryURL,
            method: "GET"
        }).then(function (result) {
            console.log(result);
            console.log(result.articles);
            for (i = 0; i < result.articles.length; i++) {
                articleNumber++;
                var article = $("<div>");
                article.addClass("well well-lg row");
                var title = $("<h3>");
                title.addClass("title");
                title.text(result.articles[i].title);
                var description = $("<p>");
                description.addClass("description");
                description.text(result.articles[i].description);
                var number = $("<div class='articleNumber'>").text(articleNumber);
                $(article).append(number, title, description);
                $("#article-results").append(article);
            }
        });
    });


});

```