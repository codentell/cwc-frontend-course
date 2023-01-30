+++
title = "05. Giphy API 👩‍🏫🧑‍🏫"
weight = 5
tags = ["server side apis"] 
+++


```js
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <title>Giphy API</title>
</head>

<body>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript" src="./script.js">
    // Example queryURL for Giphy API
    var queryURL = "https://api.giphy.com/v1/gifs/trending?api_key=dc6zaTOxFJmzC";

    $.ajax({
      url: queryURL,
      method: "GET"
    }).then(function(response) {
      console.log(response);
    });
  </script>

</body>

</html>
```