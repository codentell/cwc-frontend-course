+++
title = "02. Custom Webpage 👩‍🎓👨‍🎓"
weight = 2
tags = ["bootstrap"] 
+++

# Custom Webpage

In this activity, you will customize the default Bootstrap 4 cards, content, and footer components to better reflect your site’s content.

## Instructions

### Custom Cards

1. Find the `container-fluid <div>` and add the class `content`.

2. Within the `container-fluid <div>`, but before the `row <div>`, add an `<h2>` tag.
- Add the class `sectionHeading`.
- Add the text `Shows Near You`.

3. Next, add the `showsNear` class to the `row <div>`.

4. Update the column sizing for each `cardContainer <div>` to `col-lg-4 col-md-4 col-sm-12`.
- What do you think the size will be for each card on a small screen? What about a large screen?

5. Update each `<img>` tag to use pictures in the images folder.

6. Update the copy for each card and button to match the design, or get creative and add your own.

7. Add the following selectors and properties to style the cards section:
  
  ![Card Properties](../images/card-properties.png)

Now that you have finished the steps for this activity, your cards should be fully responsive with custom imagery.

  ![Card Solution](../images/card-solution.png)

### Custom Webpage Content Section

Next up, you will add to and style the content section of your website. Feel free to follow the design we specify below or add your own spin.

#### Part 1: Update the HTML

1. Add the content class to the `container-fluid <div>`.

2. Next, add a title to this `<div>` by adding an `<h2>` tag with the text `Why we're better`.

3. Give the `<h2>` tag the `sectionHeading` class.

4. Add the `valueProp` class to the `row <div>`.

5. Within the `row <div>`, add the `imageContainer` class to the `<div>` that contains an image.

> Note that the design has two more rows in this section. Duplicate the first row twice. Update the images and copy for each duplicated row.

#### Part 2: Update the CSS

1. Add the following CSS to style the `valueProp` and `sideAccent` classes:

  ![valueProp and Accent Properties](./images/prop-accent-properties.png)


2. Next, add the following to style the `imageContainer` class and images inside that element:

  ![imageContainer Properties](./images/image-container-properties.png)

3. Congrats! You should now have three rows of content on your template.

  ![Content Solution](../images/content-solution.png)

### Custom Webpage Footer

In this activity, you will customize your site’s footer with a call to action (CTA).

  ![Footer Solution](../images/footer-solution.png)

#### Part 1: Update the HTML

1. Add the `emailContain` class to the `<footer>` tag.

2. Next, add an `<h3>` tag within the `<form>` tag but above the `form-group <div>`.

3. Type `Join Our Mailing List` within the `<h3>` tag.

#### Part 2: Update the CSS

1. Add the following selectors, properties, and values to spruce up the footer and the form contained within:

  ![Footer Properties](../images/footer-properties.png)

- That’s it! Your design is complete! Refresh your browser to see all the changes you’ve made and how far your template has come.

- You have completed your Bootstrap template. 

- That’s it for our template; you now have a fully responsive Bootstrap 4 template ready for you to customize and use professionally.

- Feel free to modify it further if you’d like. You could create a different style or, alternatively, add more content to your Bootstrap template (this could be more sections, redoing of some sections, etc.).

Great work!
---



## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
# index.html
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

    <!-- Cards -->
    <div class="container-fluid content">
      <h2 class="sectionHeading">Shows Near You</h2>
      <div class="row showsNear">

        <!-- Card 1 -->
        <div class="cardContainer col-lg-4 col-md-4 col-sm-12">
          <div class="card">
            <img src="images/show1.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Melbourne, Australia</h5>
              <p class="card-text">Come see Slipknot unlease their new album "We Are Not Your Kind"</p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
        </div>
        <!-- End card 1 -->

        <!-- Card 2 -->
        <div class="cardContainer col-lg-4 col-md-4 col-sm-12">
          <div class="card">
            <img src="images/show2.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Chicago, Illinois</h5>
              <p class="card-text">Metallica finally returns to the big stage in Chicago Illinois</p>
              <a href="#" class="btn btn-primary">Buy Tickets</a>
            </div>
          </div>
        </div>
        <!-- End card 2 -->

        <!-- Card 3 -->
        <div class="cardContainer col-lg-4 col-md-4 col-sm-12">
          <div class="card">
            <img src="images/show3.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Long Beach, California</h5>
              <p class="card-text">The Red Hot Chili Peppers take the stage at the Honda Center</p>
              <a href="#" class="btn btn-primary">Buy Tickets</a>
            </div>
          </div>
        </div>
        <!-- End card 3 -->
      </div>
    </div>
    <!-- End cards -->

    <!-- Content -->
    <div class="container-fluid content">
      <h2 class="sectionHeading">Why we're better</h2>

      <!-- Row 1 -->
      <div class="row valueProp">
        <div class="sideAccent">
        </div>
        <div class="imageContainer col-3">
          <img src="images/assistance.png">
        </div>
        <div class="text col-8">
          <h3>We are always here to help!</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod Lorem ipsum dolor sit amet.
          </p>
          <a href="#" class="btn btn-primary">Contact Us
          </a>
        </div>
      </div>
      <!-- End row 1 -->

      <!-- Row 2 -->
      <div class="row valueProp">
        <div class="sideAccent">
        </div>
        <div class="imageContainer col-3">
          <img src="images/refund.png">
        </div>
        <div class="text col-8">
          <h3>The best prices!</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod Lorem ipsum dolor sit amet.
          </p>
          <a href="#" class="btn btn-primary">Learn More</a>
        </div>
      </div>
      <!-- End row 2 -->

      <!-- Row 3 -->
      <div class="row valueProp">
        <div class="sideAccent">
        </div>
        <div class="imageContainer col-3">
          <img src="images/mail-box.png">
        </div>
        <div class="text col-8">
          <h3>The best shows!</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod Lorem ipsum dolor sit amet.
          </p>
          <a href="#" class="btn btn-primary">More shows</a>
        </div>
      </div>
      <!-- End row 3 -->

    </div>
    <!-- End content -->

    <!-- Footer -->
    <footer class="emailContain">
      <form>
        <h3 class="sectionHeading">Join Our Mailing List</h3>
        <div class="form-group">
          <label for="exampleInputEmail1">Email address</label>
          <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp"
            placeholder="Enter email">
        </div>
        <button type="submit" class="btn btn-primary">Sign Up</button>
      </form>
    </footer>
    <!-- End footer -->

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
# style.css
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

/* Cards */
.content {
  padding: 50px;
}
.sectionHeading {
  text-align: center;
}
.showsNear  {
  padding: 0px 30px 30px 30px;
}
.cardContainer {
  text-align: center;
}

/* Content */
.sideAccent {
  background: #007bff;
  width: 15px;
}
.imageContainer img {
  width: 100%;
}
.imageContainer {
  padding: 50px;
}
.valueProp {
  margin-top: 15px;
  margin-bottom: 15px;
}

/* Footer */
.emailContain {
  background: url(../images/emailBG.jpg);
  background-size: cover;
  display: flex;
  align-items: center;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 500px;
}

/* Footer form */
form {
  width: 500px;
  margin: 35px auto;
  padding: 45px;
  border: 1px solid #F2F2F2;
  -webkit-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.3), 0 0 40px rgba(0, 0, 0, 0.1) inset;
  -moz-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.3), 0 0 40px rgba(0, 0, 0, 0.1) inset;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.1), 0 0 40px rgba(0, 0, 0, 0.1);
  background-color: white;
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
{{% /expand%}}