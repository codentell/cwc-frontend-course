+++
title = "04. Dynamic Elements 👩‍🎓👨‍🎓"
weight = 4
tags = ["server side apis"] 
+++

# Dynamic Elements

## Instructions

* Using the starter code provided, follow the instructions below to re-create the functionality demonstrated by your instructor.

* Your completed application should trigger GIFs to appear related to the animal making the sound listed in the button.

* Run the `index.html` file in your browser, click a button, and see what the response object looks like in the browser's console.
    
    * Open up the data key, then open up the `0th` element. Study the keys and how the JSON is structured.

* Create a variable named `results` and set it equal to `response.data`

* Inside the for loop, create the following:
     
    * Make a `div` with jQuery and store it in a variable named `animalDiv`.
     
    * Make a paragraph tag with jQuery and store it in a variable named `p`.
     
    * Set the inner text of the paragraph to the rating of the image in `results[i]`.
     
    * Make an image tag with jQuery and store it in a variable named `animalImage`.
     
    * Set the image's src to `results[i]`'s `fixed_height.url`.
     
    * Append the `p` variable to the `animalDiv` variable.
     
    * Append the `animalImage` variable to the `animalDiv` variable.
     
    * Prepend the `animalDiv` variable to the element with an id of `gifs-appear-here`

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="utf-8">
  <title>Animal Buttons</title>
</head>

<body>
  <button data-animal="cat">meow</button>
  <button data-animal="dog">woof</button>
  <button data-animal="bird">chirp</button>
  <div id="gifs-appear-here">
  </div>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript" src="./script.js">
    
  </script>
</body>

</html>

```

### script.js
```js
// Adding click event listen listener to all buttons
$("button").on("click", function() {
  // Grabbing and storing the data-animal property value from the button
  var animal = $(this).attr("data-animal");

  // Constructing a queryURL using the animal name
  var queryURL = "https://api.giphy.com/v1/gifs/search?q=" +
    animal + "&api_key=dc6zaTOxFJmzC&limit=10";

  // Performing an AJAX request with the queryURL
  $.ajax({
    url: queryURL,
    method: "GET"
  })
    // After data comes back from the request
    .then(function(response) {
      console.log(queryURL);

      console.log(response);
      // storing the data from the AJAX request in the results variable
      var results = response.data;

      // Looping through each result item
      for (var i = 0; i < results.length; i++) {

        // Creating and storing a div tag
        var animalDiv = $("<div>");

        // Creating a paragraph tag with the result item's rating
        var p = $("<p>").text("Rating: " + results[i].rating);

        // Creating and storing an image tag
        var animalImage = $("<img>");
        // Setting the src attribute of the image to a property pulled off the result item
        animalImage.attr("src", results[i].images.fixed_height.url);

        // Appending the paragraph and image tag to the animalDiv
        animalDiv.append(p);
        animalDiv.append(animalImage);

        // Prependng the animalDiv to the HTML page in the "#gifs-appear-here" div
        $("#gifs-appear-here").prepend(animalDiv);
      }
    });
});
```
{{% /expand%}}
