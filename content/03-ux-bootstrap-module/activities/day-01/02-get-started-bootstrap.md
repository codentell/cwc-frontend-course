+++
title = "02. Get Started with Bootstrap 👩‍🎓👨‍🎓"
weight = 2
tags = ["bootstrap"] 
+++

# Get Started With Bootstrap

The goal of this activity is to help you become familiar with Bootstrap 4, a popular framework for rapidly prototyping designs.

It’s easy to start. All you need is the following link, which you’ll place in the `<head>` section of your HTML file: 

`<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">`

## Instructions

1. Copy the link above. You can also find the link and other ways to implement [Bootstrap here](getbootstrap.com).

2. Bookmark this useful link for future projects.

3. Open `starter/index.html`. 

4. Paste the Bootstrap link into the `<head>` section of your HTML file.

- That’s it! With the Bootstrap link in place, you’re now free to use Bootstrap and its components on your page.

-  **Tip:** You only need to insert the link once for each website you use Bootstrap with.

5. Open [this link](https://getbootstrap.com/docs/4.3/components/alerts/) to the Bootstrap component documentation.

6. Navigate to the `jumbotron` component. Then copy the code listed on the page.

7. Paste the code in the `<body>` of `index.html`. Save your page and refresh to see the changes.

  ![Solution Image](./images/getting-started-solution.png)

- **Note:** Keep this file open, as you’ll use it during the next few activities.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### index.css
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

### index.html

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

    <title>Bootstrap Template</title>
  </head>
  <body>

<div class="jumbotron">
  <h1 class="display-4">Hello, world!</h1>
  <p class="lead">This is a simple hero unit, a simple jumbotron-style component for calling extra attention to featured content or information.</p>
  <hr class="my-4">
  <p>It uses utility classes for typography and spacing to space content out within the larger container.</p>
  <a class="btn btn-primary btn-lg" role="button" data-toggle="modal" data-target="#exampleModal">Learn more</a>
</div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
  </body>
</html>
```
{{% /expand%}}