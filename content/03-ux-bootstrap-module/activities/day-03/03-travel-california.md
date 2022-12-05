+++
title = "03. Travel California 👩‍🎓👨‍🎓"
weight = 3
tags = ["bootstrap"] 
+++

# Code Travel California Website

In this activity, you’ll review a creative brief, and you will code a webpage for Travel Calfiornia using Boostrap 4, HTML, and CSS.

- A creative brief’s purpose is to help guide your design decisions when you receive a design from a product manager or client. A creative brief communicates how a design should look, feel, and emulate the style of the design they’re looking for. 

- As a developer, we use redlined wireframes to better understand the layout handed off to us, so we have a visual idea of how we want to go about coding up the page. When we see a design as a series of boxes, it helps us digest a task that can sometimes feel overwhelming at first glance.

## Review the Brief

TRAVEL CALIFORNIA

Hello, we are Travel California and we need a website developer to bring our vision of our new webpage to life. Our in-house designer did a pretty good job, but feel free to tweak our design if you feel like you have ideas that can make us better. 

We like:
- Strong, legible fonts.
- Clear, well-defined sections.
- Lifestyle imagery that shows off the sights and scenery of California. The imagery must be crisp and make our viewers want to explore California.

Ways you can contribute:
- Many of our sections could use extra UI elements or features. Everything looks nice, but we wouldn’t mind more ways to interact with the webpage.
- Color scheme: If you want to explore another color palette, feel free! But try to stick to the style we have laid out in the design.
- Our typography looks nice, but we are always open to other suggestions. Maybe you can add a font that feels more... adventurous? 

Your final solution should look similar to this:

![Travel California Final](../images/travel-california-solution.png)

## Wireframes

Your assets and wireframes have already been finished for you. Normally you would need to do this yourself. You can see the images and wireframes in the appropriate folders.

## Instructions

### Part 1: Build the HTML 

It’s time to build the structure of your webpage. 

**Notes**

- Use custom HTML and Bootstrap to start the build process.

- While you do have creative control over the end product, keep in mind that the client is looking for specific things that are detailed in the creative brief.

- Most web developers build the containers and structure of their design before they style the webpage aesthetics. Building the site structure is the hardest part of being a front-end web developer, so don’t be surprised if you struggle a bit with this step! It’s normal. Redline the designs that you are handed!

- Below, you will find some tips on how you could build this layout. These rules, however, are not set in stone, and there are multiple ways to build the website.

1.  Start with a jumbotron that contains the following HTML tags: https://getbootstrap.com/docs/4.3/components/jumbotron/.
- A `header` component that you will customize later.
- Add a `nav` tag with the id `mainNav`.
  - Add a `div` tag with the class `container`.
    - Add a `link` tag with the text: travel california. 
  - Add a `div` tag.
    - Inside the `div` create an `unordered list` tag.
    - Add three `list items` for each link.
- Add a `header` tag with the class `masthead`.
  - Add a `div` tag with the class `container`.
    - Add a `div` tag with the class `row`.
      - Add a `div` tag with class `col-lg-7`.
        - An `h1` tag to hold “Download the Travel California app and explore California today!”
      - Add a `div` tag with class `col-lg-5`.
        - Add a `div` tag with the class `device-container`.
          - Add a `div` tag with the class `device`.
          - Add a `div` tag with the class `screen`.
          - Inside the div, add an `image` tag.
          - Give your image the path `src="img/demo-screen-1.png"`.

2. A `section` tag with the class `download` and id of `download` that contains the following HTML tags:

- Add a `div` tag with the class `container`.
  - Add a `div` tag with the class `row`.
    - Add a `div` tag with the class `col-md-8`.
      - An `h2` with the class `section-heading` to contain our text “Discover what all the buzz is about!”
      - A `p` to containt our text "Our app is available on any mobile device! Download now to get started!"
    - Add a `div` tag with the class `badges`.
      - Add a `link` tag with the class `badges-link`.
        - Add an `image` tag with the `src="img/google-play-badge.svg"`.
        - Add an `image` tag with the `src="img/app-store-badge.svg"`.

3. A `section` tag with the class `testimonials` that contains the following tags:

- Add a `div` tag with the class `container`.
  - An `h2` to contain our text “What people are saying...”
  - Add a `div` tag with the class `row`.
    - Create cards for each testimonial.
    - Add a `div` tag with the class `col-lg-4`.
      - Add a `div` tag with the class `testimonial-item`.
        - Add an `image` tag.
        - Add an `h5` with the name of the testimonal user.
        - Add a `p` tag with text.
    - Repeat this process for the next two cards.

4. A `section` tag with the class `signup-section` and id `signup` that contains the following tags:

- Add a `div` tag with the class `container`.
  - Add a `div` tag with the class `row`.
    - Add a `div` tag with the class `col-lg-8`.
      - Add an `i` tag; you can use this to add an icon from the font-awesome library.
      - Add an `h2` tag with the copy "Subscribe to receive updates!"
      - Add a `form` tag.
        - Add an `input` tag inside the form tag.
        - Add a `button` tag with the text "Subscribe."

5. A `section` tag with the class `contact-section` and `bg-black` that contains the following tags:

- Add a `div` tag with the class `container`.
  - Create a row to house the three cards in the design.
  - Add a `div` tag with the class `row`.
    - Add a `div` tag with the class `col-md-4`.
      - Add a `div` tag with the class `card`.
        - Add a `div` tag with the class `card-body`.
          - Add an `i` tag and use the font-awesome library to add an icon.
          - Add an `h4` tag with the class `text-uppercase` and fill in the copy.
          - Add a `div` tag and inset the copy from the design.
  - Repeat this process for the next two cards in the design.
  - Add a `div` tag with the class `social`.
    - Add three `link` tags.
    - Add an `i` tag inside each link and add a font-awesome class to add an icon.

6. A `div` with the class of `footer` that contains another div holding a `p` tag that says "Copyright" [Insert Your Name 2021].

### Part 2: Build the CSS (Style the Webpage)

For this section you will need to sign up for the software **[Figma](https://www.figma.com)**. Figma is a powerful design software that UX designers will use to create webpages before they are coded.

Once you have signed up, follow the instructions below to access the Travel California Figma File:

1. Open the [figma file](https://www.figma.com/file/xRhD5mUQHtdAImH8DUZQz8/Redline-Zeplin-Wireframe-Template?node-id=102%3A330) for Travel California.
2. Click the menu button in the top left. Select FILE > SAVE LOCAL COPY.
3. Import the file into your Figma Dashboard
4. Open the file.

The Inspect tab in Figma lets you view and copy the existing code and values for your designs. Copy single line items or entire sets of values to make the development process easier.

5. The Inspect panel can be opened from the right sidebar with a simple click on the "Inspect" tab at the top.

- Using this panel, you can easily inspect the properties of any element from your design.

![Figma Inspect Tab](../images/figma-inspect-tab.png)

6. Use Figma's Inspect panel to view and copy values for your selection.

![Figma Properties](../images/figma-properties.png)

  - Properties include values for an object's dimensions and constraints.
  - View the Content in a text layer.
  - View the Typography values for a text layer, including font, weight, line height, and more.
  - Use the Color section to view values in Hex, RGB, CSS, HSL, and HSB color models.
  - Copy values for an object's Shadows (inner and drop shadow) and Borders (stroke).
  - View the details of any prototyping Animation, including the trigger, action, and destination. You can also see the animation, the easing curve, and duration of the transition.
  - View CSS for your selection.
    - Be careful with these properties. You will be using CSS to do much of the positioning for you.

7. Add imagery and fonts to your website.

- The images you will need can be found in the `images` folder.
- To find custom fonts, check the Travel California Adobe Figma Inspect or visit https://fonts.google.com to select your own. 

8. Review the resources for extra help and good luck!

### Resources

- [How to use font-awesome](https://www.w3schools.com/icons/fontawesome_icons_intro.asp)

- [Figma tutorial: Handoff seamlessly to developers](https://www.youtube.com/watch?v=B242nuM3y2s)

- [How to use Figma’s Inspect panel](https://webdesign.tutsplus.com/tutorials/how-to-use-figmas-inspect-panel--cms-36323)

- **Tip:** If you get stuck, use your Google-fu to find answers about how to style specific elements (e.g., Google phrases like, “How to make a container span the full width of its parent” or “How to underline an h1 tag”).

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
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
    integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  <link href="https://fonts.googleapis.com/css?family=Anton|Jura&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="css/index.css">

  <!-- Custom fonts for this template -->
  <link href="vendor/fontawesome-free/css/all.min.css" rel="stylesheet">
  <link rel="stylesheet" href="vendor/simple-line-icons/css/simple-line-icons.css">
  <link href="https://fonts.googleapis.com/css?family=Lato" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css?family=Catamaran:100,200,300,400,500,600,700,800,900" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css?family=Muli" rel="stylesheet">

  <!-- Custom styles for this template -->
  <link href="css/index.css" rel="stylesheet">

  <title>Travel California</title>

</head>

<body id="page-top">

  <!-- Navigation -->
  <nav class="navbar navbar-expand-lg navbar-light fixed-top" id="mainNav">
    <div class="container">
      <a class="navbar-brand js-scroll-trigger" href="#page-top">Travel California</a>
      <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse"
        data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false"
        aria-label="Toggle navigation">
        Menu
        <i class="fas fa-bars"></i>
      </button>
      <div class="collapse navbar-collapse" id="navbarResponsive">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#download">Download</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#features">Features</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#contact">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <!-- Hero Section -->
  <header class="masthead">
    <div class="container h-100">
      <div class="row h-100">
        <div class="col-lg-7 my-auto">
          <div class="header-content mx-auto">
            <h1 class="mb-5">Download the Travel California App and explore California today!</h1>
            <a href="#download" class="btn btn-outline btn-xl js-scroll-trigger">Download for Free!</a>
          </div>
        </div>
        <div class="col-lg-5 my-auto">
          <div class="device-container">
            <img src="images/demo-screen-1 1.png" class="img-fluid" alt="">
          </div>
        </div>
      </div>
    </div>
  </header>

  <!-- Download Section -->
  <section class="download bg-primary text-center" id="download">
    <div class="container">
      <div class="row">
        <div class="col-md-8 mx-auto">
          <h2 class="section-heading">Discover what all the buzz is about!</h2>
          <p>Our app is available on any mobile device! Download now to get started!</p>
          <div class="badges">
            <a class="badge-link" href="#"><img src="images/google-play-badge.png" alt=""></a>
            <a class="badge-link" href="#"><img src="images/app-store-badge.png" alt=""></a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Testimonials -->
  <section class="testimonials text-center bg-light">
    <div class="container">
      <h2 class="mb-5">What people are saying...</h2>
      <div class="row">
        <div class="col-lg-4">
          <div class="testimonial-item mx-auto mb-5 mb-lg-0">
            <img class="img-fluid rounded-circle mb-3" src="images/testimonials-1.jpg" alt="">
            <h5>Margaret E.</h5>
            <p class="font-weight-light mb-0">"This is fantastic! Thanks so much guys!"</p>
          </div>
        </div>
        <div class="col-lg-4">
          <div class="testimonial-item mx-auto mb-5 mb-lg-0">
            <img class="img-fluid rounded-circle mb-3" src="images/testimonials-3.jpg" alt="">
            <h5>Sarah W.</h5>
            <p class="font-weight-light mb-0">"Thanks so much for making these free resources available to us!"</p>
          </div>
        </div>
        <div class="col-lg-4">
          <div class="testimonial-item mx-auto mb-5 mb-lg-0">
            <img class="img-fluid rounded-circle mb-3" src="images/testimonials-2.jpg" alt="">
            <h5>Fred S.</h5>
            <p class="font-weight-light mb-0">"Travel California is amazing. I've been using it to create lots of super
              nice landing pages."</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Call to Action -->
  <section class="signup-section" id="signup">
    <div class="container">
      <div class="row">
        <div class="col-md-10 col-lg-8 mx-auto text-center">
          <i class="far fa-paper-plane fa-2x mb-2 text-white"></i>
          <h2 class="text-white mb-5">Subscribe to receive updates!</h2>
          <form class="form-inline d-flex">
            <input class="form-control flex-fill mr-0 mr-sm-2 mb-3 mb-sm-0" id="inputEmail" type="email"
              placeholder="Enter email address..." />
            <button class="btn btn-primary mx-auto" type="submit">Subscribe</button>
          </form>
        </div>
      </div>
    </div>
  </section>
  <!-- Contact-->
  <section class="contact-section bg-black">
    <div class="container">
      <div class="row">
        <div class="col-md-4 mb-3 mb-md-0">
          <div class="card py-4 h-100">
            <div class="card-body text-center">
              <i class="fas fa-map-marked-alt text-primary mb-2"></i>
              <h4 class="text-uppercase m-0">Address</h4>
              <hr class="my-4" />
              <div class="small text-black-50">4923 Market Street, Sacramento,</div>
            </div>
          </div>
        </div>
        <div class="col-md-4 mb-3 mb-md-0">
          <div class="card py-4 h-100">
            <div class="card-body text-center">
              <i class="fas fa-envelope text-primary mb-2"></i>
              <h4 class="text-uppercase m-0">Email</h4>
              <hr class="my-4" />
              <div class="small text-black-50"><a href="#!">hello@california.com</a></div>
            </div>
          </div>
        </div>
        <div class="col-md-4 mb-3 mb-md-0">
          <div class="card py-4 h-100">
            <div class="card-body text-center">
              <i class="fas fa-mobile-alt text-primary mb-2"></i>
              <h4 class="text-uppercase m-0">Phone</h4>
              <hr class="my-4" />
              <div class="small text-black-50">+1 (800) CALI-FORNIA </div>
            </div>
          </div>
        </div>
      </div>
      <div class="social d-flex justify-content-center">
        <a class="mx-2" href="#!"><i class="fab fa-twitter"></i></a>
        <a class="mx-2" href="#!"><i class="fab fa-facebook-f"></i></a>
        <a class="mx-2" href="#!"><i class="fab fa-github"></i></a>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <p>&copy; Your Website 2020. All Rights Reserved.</p>

    </div>
  </footer>
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

# index.css
```css
/* Global styles ============= */
html,
body {
  width: 100%;
  height: 100%;
}

body {
  font-family: 'Muli', 'Helvetica', 'Arial', 'sans-serif';
}

a {
  color: #fdcc52;
  transition: all .35s;
}

a:hover, a:focus {
  color: #fcbd20;
}

hr {
  max-width: 100px;
  margin: 25px auto 0;
  border-width: 1px;
  border-color: rgba(34, 34, 34, 0.1);
}

hr.light {
  border-color: white;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: 'Catamaran', 'Helvetica', 'Arial', 'sans-serif';
  font-weight: 200;
  letter-spacing: 1px;
}

p {
  font-size: 18px;
  line-height: 1.5;
  margin-bottom: 20px;
}

section {
  padding: 100px 0;
}

section h2 {
  font-size: 50px;
}

/* Navigation bar styles ============= */
#mainNav {
  border-color: rgba(34, 34, 34, 0.05);
  background-color:#64a19d;
  transition: all .35s;
  font-family: 'Catamaran', 'Helvetica', 'Arial', 'sans-serif';
  font-weight: 200;
  letter-spacing: 1px;
} 

#mainNav .navbar-brand {
  color: #fdcc52;
  font-family: 'Catamaran', 'Helvetica', 'Arial', 'sans-serif';
  font-weight: 200;
  letter-spacing: 1px;
}

#mainNav .navbar-brand:hover, #mainNav .navbar-brand:focus {
  color: #fcbd20;
}

#mainNav .navbar-toggler {
  font-size: 12px;
  padding: 8px 10px;
  color: #222222;
}

#mainNav .navbar-nav > li > a {
  font-size: 11px;
  font-family: 'Lato', 'Helvetica', 'Arial', 'sans-serif';
  letter-spacing: 2px;
  text-transform: uppercase;
}

#mainNav .navbar-nav > li > a.active {
  color: #fdcc52 !important;
  background-color: transparent;
}

#mainNav .navbar-nav > li > a.active:hover {
  background-color: transparent;
}

#mainNav .navbar-nav > li > a,
#mainNav .navbar-nav > li > a:focus {
  color: #222222;
}

#mainNav .navbar-nav > li > a:hover,
#mainNav .navbar-nav > li > a:focus:hover {
  color: #fdcc52;
}

/* Hero section ============= */

header.masthead {
  position: relative;
  width: 100%;
  padding-top: 150px;
  padding-bottom: 100px;
  color: white;
  background: url("../images/bg-img.svg");
}

header.masthead .header-content {
  max-width: 500px;
  margin-bottom: 100px;
  text-align: center;
}

header.masthead .header-content h1 {
  font-size: 30px;
}

header.masthead .device-container {
  max-width: 325px;
  margin-right: auto;
  margin-left: auto;
}

header.masthead .device-container .screen img {
  border-radius: 3px;
}


section.download {
  position: relative;
  padding: 150px 0;
}

section.download h2 {
  font-size: 50px;
  margin-top: 0;
}

section.download .badges .badge-link {
  margin-bottom: 25px;
}

section.download .badges .badge-link:last-child {
  margin-bottom: 0;
}

section.download .badges .badge-link img {
  height: 60px;
}


/* Testimonials section ============= */

section.testimonials {
  padding-top: 7rem;
  padding-bottom: 7rem;
}

section.testimonials .testimonial-item {
  max-width: 18rem;
}

section.testimonials .testimonial-item img {
  max-width: 12rem;
  box-shadow: 0px 5px 5px 0px #adb5bd;
}

/* Signup section ============= */


.signup-section {
  padding: 10rem 0;
  background: linear-gradient(to bottom, rgba(0, 0, 0, 0.1) 0%, rgba(0, 0, 0, 0.5) 75%, #000000 100%), url("../images/sf.svg");
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: scroll;
  background-size: cover;
}
.signup-section .form-inline input {
  box-shadow: 0 0.1875rem 0.1875rem 0 rgba(0, 0, 0, 0.1) !important;
  padding: 1.25rem 2rem;
  height: auto;
  font-family: "Varela Round", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 80%;
  text-transform: uppercase;
  letter-spacing: 0.15rem;
  border: 0;
}

.contact-section {
  padding-top: 5rem;
}
.contact-section .card {
  border: 0;
  border-bottom: 0.25rem solid #64a19d;
}
.contact-section .card h4 {
  font-size: 0.8rem;
  font-family: "Varela Round", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  text-transform: uppercase;
  letter-spacing: 0.15rem;
}
.contact-section .card hr {
  border-color: #64a19d;
  border-width: 0.25rem;
  width: 3rem;
}
.contact-section .social {
  margin-top: 5rem;
}
.contact-section .social a {
  text-align: center;
  height: 3rem;
  width: 3rem;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 100%;
  line-height: 3rem;
  color: rgba(255, 255, 255, 0.3);
}
.contact-section .social a:hover {
  color: rgba(255, 255, 255, 0.5);
}
.contact-section .social a:active {
  color: #fff;
}

.bg-black {
  background-color: #000000 !important;
}

footer {
  padding: 25px 0;
  text-align: center;
  color: rgba(255, 255, 255, 0.3);
  background-color: #222222;
}

footer p {
  font-size: 12px;
  margin: 0;
}

footer ul {
  margin-bottom: 0;
}

footer ul li a {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.3);
}

footer ul li a:hover, footer ul li a:focus, footer ul li a:active, footer ul li a.active {
  text-decoration: none;
}

.bg-primary {
  background: #fdcc52;
  background: linear-gradient(#fdcc52, #fdc539);
}

.text-primary {
  color: #fdcc52;
}

.no-gutter > [class*='col-'] {
  padding-right: 0;
  padding-left: 0;
}


.btn {
  box-shadow: 0 0.1875rem 0.1875rem 0 rgba(0, 0, 0, 0.1) !important;
  padding: 1.25rem 2rem;
  font-family: "Varela Round", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 80%;
  text-transform: uppercase;
  letter-spacing: 0.15rem;
  border: 0;
}

.btn-outline {
  color: white;
  border: 1px solid;
  border-color: white;
}

.btn-outline:hover, .btn-outline:focus, .btn-outline:active, .btn-outline.active {
  color: white;
  border-color: #fdcc52;
  background-color: #fdcc52;
}

.btn {
  border-radius: 300px;
  font-family: 'Lato', 'Helvetica', 'Arial', 'sans-serif';
  letter-spacing: 2px;
  text-transform: uppercase;
}

.btn-xl {
  font-size: 11px;
  padding: 15px 45px;
}
```
{{% /expand%}}
