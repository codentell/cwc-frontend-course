+++
title = "02. Row Columns 👩‍🎓👨‍🎓"
weight = 2
tags = ["css"] 
+++

# Bootstrap Containers and Rows

Your page has a `navbar` and `jumbotron`, so it’s time to add a structure for its content.

Understanding how to structure a layout using containers, rows, and columns is necessary to create effective layouts with Bootstrap, as they are the default way to add structure to your site using Bootstrap 4.

## Bootstrap Grid Reference

  ![Grid Reference](../images/grid-reference.png)

Here is a quick reference for each Bootstrap 4 class used to build containers and rows:

- `Container`: Containers provide a means to center and horizontally pad your site’s contents.

- `Container-fluid`: Fluid containers function almost the same way as regular containers, except that they span the entire width of your device’s viewport.

- `Row`: Rows are wrappers for columns.

- `Column`: Columns are nested within rows and determine the width of your content within a row (Bootstrap rows can be divided into 12 columns). 

- Read more about column widths and screen sizes [here](https://getbootstrap.com/docs/4.3/layout/grid/#grid-options).

## Instructions

1. Add a `<div>` with the class `container-fluid` after your `jumbotron`.

2. Within this new `<div>`, add another `<div>` with the class `row`.

3. At this point, you should have two `<div>` tags, one nested in the other. 

4. Lastly, add a `<div>` with the classes `cardContainer col-lg-3 col-md-3 col-sm-12` within the row div. 

5. **BONUS:** Can you tell what the `col-lg-3 col-md-3 col-sm-12` classes are doing to the `<div>`? 

- Take a look at the Bootstrap documentation for an answer. 

- **Hint:** Look up `lg`, `md`, and `sm` references.

6. Your final step is to copy and paste this newly created `<div>` three times within the `row div`. 

7. You should now have a `row <div>` with four children `<div>` tags. 

8. If you want to see what is happening on your page, add some dummy copy within the child divs.

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
      <div>
        <div></div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div>
        <div>
          
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div>
        <div>
          
        </div>
      </div>
    </div><!-- Close row -->

  <div class="row">
    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div>
        <div>
          
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div>
        <div>
          
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div>
        <div>
          
        </div>
      </div>
    </div>

    <div class="cardContainer col-lg-3 col-md-3 col-sm-12">
      <div>
        <div>
          
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