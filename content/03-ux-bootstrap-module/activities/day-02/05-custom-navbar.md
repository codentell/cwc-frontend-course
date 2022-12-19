+++
title = "05. Custom Navbar 👩‍🎓👨‍🎓"
weight = 5
tags = ["css"] 
+++

# Custom Webpage Navbar

Every website needs an intuitive and well-crafted navigation layout so that users can quickly get to the content they’re seeking. Bootstrap’s default navigation component offers a pretty good solution, but what if it doesn’t match your design’s layout and mood? 

In this activity, you’ll customize your site’s navbar to better reflect the site’s layout and overall brand identity.

  ![Custom Navbar Solution](../images/custom-navbar-solution.png)

## Instructions

### Part 1: Update the HTML

1. Open the `starter` folder and navigate to `index.html`. 
- You will build on this file for all of today’s activities.

2. Add the `customNav` class to the `<nav>` element.
- You will use this new class to style your navbar later.

3. Update the first `<a>` tag by replacing the Navbar text with the following:
- An `<img src="images/acoustic-guitar.png”> tag`.
- Add the text `Rock Nation`.

4. Make the following text changes to the list items in the navbar:
- Change `Home` to `Venues`, `Link` to `Artist`, and `Dropdown` to `Near You`.

5. Change the three `dropdown` options to `Venues`, `Artists`, and `Upcoming Acts`.
- **Hint:** You can find these dropdown items in the dropdown menu `<div>`.

6. Next, delete the `<form>` element from the template navbar.

7. Lastly, you will add a new navigation list item with a button inside:
- Add a `<li>` tag after the dropdown `<li>`.
- Give it the same class name as the other `<li>` elements in the navbar.
- Add a `<a>` tag with the following properties:
  - `btn btn-primary btn-lg navCTA classes`
  - `href="#"`
  - `role="button"`
  - `Buy Tickets` text

8. You can view your changes in your browser, but there won’t be much to see yet!

### Part 2: Update the CSS

1. Open `index.css`.
- You will notice three selectors already created. Add your custom CSS above these prewritten selectors.

2. Create a selector that targets all the heading tags (`<h1>` through `<h6>`).

- You can target multiple elements, classes, or IDs with the following syntax:

 `element1, element2, ... {
   .example-class
}`

3. Add the property `font-family` and set its value to `'Anton', sans-serif;`.

4. Add a selector that targets the `<p>` element and sets its `font-family` to `'Jura', sans-serif;`.

5. Add the following selectors, properties, and values to begin styling your navbar:

> Note the use of `!important` to force some CSS rules to apply.

- [What does `!important` mean?](https://www.lifewire.com/what-does-important-mean-in-css-3466876)

  ![!important CSS](../images/important-css.png)

6. Setting the `z-index value` for the `customNav` class ensures that the navbar is above other content on the page.

7. Next, customize the drop-down menu with the following CSS:
	
  ![Dropdown Customization](../images/dropdown-customization.png)

- The `:focus` and `:hover` pseudo-classes allow us to apply particular styling when a user interacts with an element.

8. Lastly, customize the button and links in the navigation with the following:

  ![Button Customization](../images/button-customization.png)

Now you have a fully customized navbar for your site!


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