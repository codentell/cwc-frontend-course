+++
title = "04. Ajax HTML 👩‍🎓👨‍🎓"
weight = 4
tags = ["server side apis"] 
+++

# AJAX to HTML

## Instructions

* Using the starter code in provided, create and append a new table row to the existing table body. The new row should display the retrieved movie's `Title`, `Year`, and `Actors`.

* Once you have successfully created and populated a new table row, repeat this process to query the OMDb API for two more movies of your choice! Append two more rows containing the results from both AJAX requests.

### 💡 Hint 

You will have to build a URL of your own with the search parameters listed.

### 🏆 Bonus

* If you've you've completed the activity ahead of time, refactor your solution to be more DRY by placing repetitive logic inside of functions to be called when needed.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```html
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
{{% /expand%}}