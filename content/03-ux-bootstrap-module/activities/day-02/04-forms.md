+++
title = "04. Forms 👩‍🎓👨‍🎓"
weight = 4
tags = ["css"] 
+++

# Bootstrap Forms and Modals

In this activity, you will add HTML and CSS on top of Bootstrap so that your page is more responsive. 

Companies never use Bootstrap in its basic form, so it’s smart to practice customizing it with HTML and CSS. 

## Instructions

### Add a Form to Your Page

1. In your `index.html` file, create a section with the class of `container-fluid` and `signUp`.
- Nested inside of it, create a div with the class of row. We will nest our form inside this element.

2. Open the Bootstrap form component page: https://getbootstrap.com/docs/4.3/components/forms/.

3. Navigate to the first form element you find on the page.
 
 ![Form Solution](../images/form-solution.png)

4. Copy it and paste it into your HTML below your cards. Look for the comment `<!-- Add form group below →`.

5. Open the `index.css` file.

6. Create a `class` that targets the `<form>` element wrapped inside the class of `signUp`.

- Give this CSS selector the property `margin` with a property of `35px auto` to center our form element and give it some spacing.
- Give this CSS selector the `background-color` property with a value of `#f2f2f2`.
- Give this CSS selector the property of `padding` with a value of `25px`.
- Give this CSS selector a `border-radius` of `7px`.

### Add a Modal to Your Page

7. At the bottom of our document, you’ll notice that we already have the script tags to use Bootstrap components that require JavaScript. Without these tag components that require JavaScript, the code will not work. The tags follow, just in case you don’t have these in your template already:
- `<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>`
- `<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>`
- `<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>`

8. Open Bootstrap’s modal component page: https://getbootstrap.com/docs/4.3/components/modal/#live-demo.

9. Copy the modal element of the live demo and paste it into your HTML.

10. Delete the button element, so you can link the modal to your own button pictured below.

  ![Button Element](../images/button-element.png)
 
11. This button has two important attributes to take note of:
- `data-toggle=”modal”`
- `data-target=”#exampleModal”`

12. Add these two attributes to the button in the `jumbotron`.

 ![Jumbotron Attributes](../images/jumbotron-attributes.png)

> **Note:** The attribute data target must match the ID of the jumbotron you want it to toggle. You can have multiple modal windows, but each must have a different ID and data target.
  
  ![Modal Id](../images/modal-id.png)

13. Reload your page and see the result. Make sure you click the `jumbotron` button! You should see your modal animate before your eyes.

14. Now that that modal is working, copy another Bootstrap form element and style it to look real!

- https://getbootstrap.com/docs/4.4/components/forms/

15. Style it however you want or use this opportunity to teach yourself some new CSS tricks.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
## index.css
```css
footer {
  position: absolute;
  width: 100%;
  height: 60px;
  line-height: 60px;
  background-color: #f5f5f5;
  margin-top: 50px;
}
.cardContainer {
  margin-bottom: 15px;
}
.card {
  margin: 0 auto;
}
.signUp form {
  margin: 35px auto;
  background-color: #f2f2f2;
  padding: 25px;
  border-radius: 7px;
}
Footer

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
    <link rel="stylesheet" href="css/index.css">

    <title>Hello, world!</title>
  </head>
  <body>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
  <ul class="navbar-nav mr-auto">
    <li class="nav-item active">
      <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="#">Link</a>
    </li>
    <li class="nav-item dropdown">
      <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Dropdown
      </a>
      <div class="dropdown-menu" aria-labelledby="navbarDropdown">
        <a class="dropdown-item" href="#">Action</a>
        <a class="dropdown-item" href="#">Another action</a>
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Something else here</a>
      </div>
    </li>
    <li class="nav-item">
      <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
    </li>
  </ul>
  <form class="form-inline my-2 my-lg-0">
    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
  </form>
  </div>
  </nav>

<div class="jumbotron">
  <h1 class="display-4">Hello, world!</h1>
  <p class="lead">This is a simple hero unit, a simple jumbotron-style component for calling extra attention to featured content or information.</p>
  <hr class="my-4">
  <p>It uses utility classes for typography and spacing to space content out within the larger container.</p>
  <a class="btn btn-primary btn-lg" role="button" data-toggle="modal" data-target="#exampleModal">Learn more</a>
</div>

<div class="container-fluid">
  <div class="row">
    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/1_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/2_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/3_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/2_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>
  </div><!-- Close row -->

  <div class="row">
    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/4_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/5_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/6_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div class="card">
        <img src="images/2_card.png" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
    </div>
  </div><!-- close row -->
</div><!-- Close container fluid -->

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
  </body>
</html>
```

{{% /expand%}}