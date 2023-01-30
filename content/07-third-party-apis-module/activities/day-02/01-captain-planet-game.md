+++
title = "01. Captain Planet Game 👩‍🎓👨‍🎓"
weight = 1
tags = ["third party apis"] 
+++

# Captain Planet Game

## Instructions

* Create a new superpower for Captain Planet using jQuery.

  * Look at the [jQuery API documents](https://api.jquery.com/) if you get stuck 
  
* Examples:
  * Click to… Stretch Captain Planet!
  * Click to… Trigger a maniacal laugh!
  * Click to… Create clones of Captain Planet!
  * Click to… Create fire or water (hint: images)!

* Slack out a screenshot of the working example.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
```html
<!DOCTYPE html>
<html lang="en-gb">

  <head>
    <meta charset="UTF-8">
    <title>Captain Planet: The Game</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
    <!-- Bootstrap File -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

  </head>

  <body>

    <!-- Overall Bootstrap Grid -->
    <div class="container">

      <!-- Jumbotron with Title -->
      <div class="jumbotron">
        <h1 class="text-center">
          <strong>Captain Planet</strong>
        </h1>
        <hr>
        <div id="musicControls" class="text-center">
          <button class="btn btn-warning btn-xs theme-button">
            <span class="fa fa-music"></span> Play Theme!</button>
          <button class="btn btn-dark btn-xs pause-button">
            <span class="fa fa-pause"></span> Pause Song</button>
        </div>

      </div>
      <div class="row">

        <div class="col-lg-6">

          <!-- Controls (Superpower Grow/Shrink)-->
          <div id="sizeControls" class="card">
            <h4 class="card-header">Superpowers - Change Sizes!</h4>
            <div class="card-body">
              <div class="text-center">
                <button class="btn btn-dark btn-lg normal-button">
                  <span class="fa fa-ok"></span> Normal</button>
                <button class="btn btn-primary btn-lg grow-button">
                  <span class="fa fa-plus"></span> Grow</button>
                <button class="btn btn-danger btn-lg shrink-button">
                  <span class="fa fa-minus"></span> Shrink</button>
              </div>
            </div>
          </div>

          <!-- Controls (Superpower Visibility) -->
          <div id="visibilityControls" class="card">
            <h4 class="card-header">Superpowers - Invisiblity!</h4>
            <div class="card-body">
              <div class="text-center">
                <button class="btn btn-dark btn-lg vis-button">
                  <span class="fa fa-eye"></span> Visible</button>
                <button class="btn btn-info btn-lg invis-button">
                  <span class="fa fa-eye-slash"></span> Invisible</button>
              </div>
            </div>
          </div>

          <!-- Controls (Superpower Move Controls) -->
          <div id="moveControls" class="card">
            <h4 class="card-header">Move Controls</h4>
            <div class="card-body">
              <div class="text-center mb-1">
                <button class="btn btn-dark btn-lg fa fa-arrow-up up-button">Up</button>
              </div>
              <div class="text-center">
                <button class="btn btn-dark btn-lg fa fa-arrow-left left-button">Left</button>
                <button class="btn btn-dark btn-lg fa fa-arrow-down down-button">Down</button>
                <button class="btn btn-dark btn-lg fa fa-arrow-right right-button">Right</button>
              </div>
              <br>
              <div class="text-center">
                <button class="btn btn-dark btn-lg back-button">
                  <span class="fa fa-comment"></span> Go Planet!</button>
              </div>
            </div>
          </div>
        </div>

        <!-- Right Card (Captain Planet Hero)-->
        <div class="col-lg-6">

          <!-- Captain Planet Image -->
          <img src="assets/captain-planet.jpg" alt="" class="img captain-planet" style="position:absolute; top:50px; left: 80px; z-index: -20; height: 300px">
        </div>
      </div>
    </div>

    <!-- Added link to the jQuery library -->
  <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
  <script type="text/javascript" src="./assets/js/script.js"></script>

  </body>

</html>

```
```js
// JavaScript function that wraps everything
  $(document).ready(function() {

    var captainPlanet = $(".captain-planet");

    // Gets Link for Theme Song
    var audioElement = document.createElement("audio");
    audioElement.setAttribute("src", "assets/captainplanet24.mp3");

    // Theme Button
    $(".theme-button").on("click", function() {
      audioElement.play();
    });
    $(".pause-button").on("click", function() {
      audioElement.pause();
    });

    // Size Buttons
    $(".normal-button").on("click", function() {
      captainPlanet.animate({ height: "300px" });
    });
    $(".grow-button").on("click", function() {
      captainPlanet.animate({ height: "500px" });
    });
    $(".shrink-button").on("click", function() {
      captainPlanet.animate({ height: "100px" });
    });

    // Visibility Buttons
    $(".vis-button").on("click", function() {
      captainPlanet.animate({ opacity: "1" });
    });
    $(".invis-button").on("click", function() {
      captainPlanet.animate({ opacity: "0.05" });
    });

    // Move Buttons
    $(".up-button").on("click", function() {
      captainPlanet.animate({ top: "-=200px" }, "normal");
    });
    $(".down-button").on("click", function() {
      captainPlanet.animate({ top: "+=200px" }, "normal");
    });
    $(".left-button").on("click", function() {
      captainPlanet.animate({ left: "-=200px" }, "normal");
    });
    $(".right-button").on("click", function() {
      captainPlanet.animate({ left: "+=200px" }, "normal");
    });
    $(".back-button").on("click", function() {
      captainPlanet.animate({ top: "50px", left: "80px" }, "fast");
    });

    // Keyboard move controls
    $(document).keyup(function(e) {
      switch (e.which) {

      // Move Buttons (Keyboard Down)
      case 40:
        captainPlanet.animate({ top: "+=200px" }, "normal");
        break;

        // Move Buttons (Keyboard Right)
      case 39:
        captainPlanet.animate({ left: "+=200px" }, "normal");
        break;

        // Move Buttons (Keyboard Up)
      case 38:
        captainPlanet.animate({ top: "-=200px" }, "normal");
        break;

        // Move Buttons (Keyboard Left)
      case 37:
        captainPlanet.animate({ left: "-=200px" }, "normal");
        break;

      default:
        break;
      }
    });
  });
```
{{% /expand%}}