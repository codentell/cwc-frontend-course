+++
title = "02. Cat Button 👩‍🎓👨‍🎓"
weight = 2
tags = ["server side apis"] 
+++

# Cat Button

## Instructions

* Open the file `cat-button.html` in your browser. Then take a few moments to see what the application does.

* Fill in the missing comments for each line to describe what each section does.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <title>The Magical Cat Button</title>
</head>

<body>
  <button id="cat-button">magical cat button</button>
  <div id="images">
  </div>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript">
    // Event listener for our cat-button
    $("#cat-button").on("click", function() {

      // Storing our giphy API URL for a random cat image
      var queryURL = "https://api.giphy.com/v1/gifs/random?api_key=dc6zaTOxFJmzC&tag=cats&rating=pg";

      // Perfoming an AJAX GET request to our queryURL
      $.ajax({
        url: queryURL,
        method: "GET"
      })

      // After the data from the AJAX request comes back
        .then(function(response) {

        // Saving the image_original_url property
          var imageUrl = response.data.images.original.url;

          // Creating and storing an image tag
          var catImage = $("<img>");

          // Setting the catImage src attribute to imageUrl
          catImage.attr("src", imageUrl);
          catImage.attr("alt", "cat image");

          // Prepending the catImage to the images div
          $("#images").prepend(catImage);
        });
    });
  </script>
</body>

</html>
```

{{% /expand%}}