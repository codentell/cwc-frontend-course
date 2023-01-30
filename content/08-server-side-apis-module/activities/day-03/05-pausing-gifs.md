+++
title = "05. Pausing Gifs 👩‍🎓👨‍🎓"
weight = 5
tags = ["server side apis"] 
+++

# Pausing Gifs

## Instructions

* Using the starter code provided, follow the instructions below to provide stop/start animation to your application.

* Create a variable named `state` and then store the image's `data-state` into it.
      
      * Use the `.attr()` method for this.

* Update the `src` attribute of an image to it's `data-animate` value
       
      * Update the `data-state` attribute to `'animate'`.

      * If `state` is equal to `'animate'`, then update the `src` attribute of the image to it's `data-still` value and update the `data-state` attribute to `'still'`

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="utf-8">
  <title>Stop: It's Giphy time</title>
</head>

<body>
  <img src="https://media1.giphy.com/media/3o85xkQpyMlnBkpB9C/200_s.gif" data-still="https://media1.giphy.com/media/3o85xkQpyMlnBkpB9C/200_s.gif" data-animate="https://media1.giphy.com/media/3o85xkQpyMlnBkpB9C/200.gif" data-state="still" class="gif">
  <img src="https://media2.giphy.com/media/8rFQp4kHXJ0gU/200_s.gif" data-still="https://media2.giphy.com/media/8rFQp4kHXJ0gU/200_s.gif" data-animate="https://media2.giphy.com/media/8rFQp4kHXJ0gU/200.gif" data-state="still" class="gif">
  <img src="https://media3.giphy.com/media/W6LbnBigDe4ZG/200_s.gif" data-still="https://media3.giphy.com/media/W6LbnBigDe4ZG/200_s.gif" data-animate="https://media3.giphy.com/media/W6LbnBigDe4ZG/200.gif" data-state="still" class="gif">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript">
    $(".gif").on("click", function() {
      // The attr jQuery method allows us to get or set the value of any attribute on our HTML element
      var state = $(this).attr("data-state");
      // If the clicked image's state is still, update its src attribute to what its data-animate value is.
      // Then, set the image's data-state to animate
      // Else set src to the data-still value
      if (state === "still") {
        $(this).attr("src", $(this).attr("data-animate"));
        $(this).attr("data-state", "animate");
      } else {
        $(this).attr("src", $(this).attr("data-still"));
        $(this).attr("data-state", "still");
      }
    });
  </script>
</body>

</html>
```
{{% /expand%}}