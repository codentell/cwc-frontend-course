+++
title = "06. Custom Jumbotron 👩‍🎓👨‍🎓"
weight = 6
tags = ["css"] 
+++

# Custom Webpage Jumbotron

In this activity, you will turn the default Bootstrap 4 jumbotron you have now into a professional-level, attention-grabbing image.  

  ![Custom Jumbotron Solution](../images/custom-jumbotron-solution.png)

## Instructions

1. Add the `rockBackground` class to the `jumbotron <div>`.
- Again, you will be using this class to style this element.

2. Add a new `<div>` with the class `jumboCopy` within the `jumbotron <div>`.

3. Move the jumbotron’s content within this new `<div>`.

4. Update the copy and button text in the jumbotron to reflect the design above. 
- **Note:** Feel free to add a more compelling description.

5. Add the following CSS within a selector that targets the `jumbotron <div>`:

  ![Jumbotron CSS Properties](../images/jumbotron-css-properties.png)

6. Add a selector for the `jumboCopy` class with the following properties and values:

  ![jumboCopy CSS Properties](../images/jumboCopy-css-properties.png)

Great work!

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
## index.css
```css
/* Text */
h1, h2, h3 , h4, h5, h6 {
  font-family: 'Anton', sans-serif;
}
p {
  font-family: 'Jura', sans-serif;
}

/* Navigation bar */

/* General */
.customNav {
  position: fixed;
  width: 100%;
  background: url("../images/transparency.png");
  background-color: transparent !important;
  background-size: cover;
  z-index: 10;
}
.navbar-nav {
  margin-left: auto;
  margin-right: 0 !important;
}
.navbar-brand img {
  padding-right: 15px;
  width: 65px;
}
.nav-item {
  margin: 0px 15px;
}

/* Navigation dropdown menu */
.dropdown-menu {
  background: url("../images/transparency.png");
  background-color: transparent !important;
  background-size: cover;
}
.dropdown-item:focus, .dropdown-item:hover {
    color: #16181b;
    text-decoration: none;
    background: black;
}

/* Navigation links */
.customNav a {
  color: white !important;
}
.navCTA {
  font-size: 15px;
}

/* Jumbotron  */
.jumbotron {
  background-image: url(../images/rockOn_dark.jpg);
  background-size: cover;
  background-repeat: no-repeat;
  height: calc(100vh - 25px);
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Jumbotron copy */
.jumboCopy {
  width: 70%;
  min-width: 500px;
  max-width: 700px;
  color: white;
  text-align: center;
}

/* STYLES FOR TEMPLATE PLEASE DO NOT TOUCH*/
.dropdown-menu {
  left: -97px;
}
footer {
  position: absolute;
  width: 100%;
  height: 60px;
  line-height: 60px;
  background-color: #f5f5f5;
  margin-top: 50px;
}
.cardContainer {
  margin-top: 20px;
}
.card {
  margin: 0 auto;
}
```

## index.html
```html
<!DOCTYPE html>
<html lang="en-gb">

  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    <link href="https://fonts.googleapis.com/css?family=Anton|Jura&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="css/index.css">

    <title>Rock Nation</title>
  </head>
  <body>

    <!-- Navigation bar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light customNav">
      <a class="navbar-brand" href="#"><img src="images/acoustic-guitar.png">Rock Nation</a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Venues <span class="sr-only">(current)</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Artists</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Near you</a>
            <div class="dropdown-menu" aria-labelledby="navbarDropdown">
              <a class="dropdown-item" href="#">Venues</a>
              <div class="dropdown-divider"></div>
              <a class="dropdown-item" href="#">Artists</a>
              <div class="dropdown-divider"></div>
              <a class="dropdown-item" href="#">Upcoming Acts</a>
            </div>
          </li>
          <li class="nav-item">
            <a class="btn btn-primary btn-lg navCTA" href="#" role="button">Buy Tickets</a>
          </li>
        </ul>
      </div>
    </nav>
    <!-- End navigation bar -->
     
    <!-- Jumbotron -->
    <div class="jumbotron rockBackground">
      <div class="jumboCopy">
        <h1 class="display-4">It's Time to Rock</h1>
        <p class="lead">Rock Nation brings you the most headbanging shows on the planet. Click below to find tickets for
          your favorite bands</p>
        <a class="btn btn-primary btn-lg" href="#" role="button">Buy Tickets</a>
      </div>
    </div>
    <!-- End jumbotron -->

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js"
      integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
      crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"
      integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1"
      crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"
      integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM"
      crossorigin="anonymous"></script>
  </body>

</html>
```
{{% /expand%}}