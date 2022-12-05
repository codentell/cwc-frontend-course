+++
title = "03. CSS Grid Part 3  👩‍🎓👨‍🎓"
weight = 3
tags = ["css"] 
+++

# CSS Grid and Breakpoints

CSS Grid can be used to build simple and skeletal layouts. It can also be used to create polished, professional-level layouts.

In this activity, you will use CSS Grid to re-create the design of an online furniture store.

## Instructions

### Part 3: Responsive Breakpoint

Let's make our page responsive!

* Write a `media query` that targets a screen size with the `max-width of 1000px`.

> **Note:** You must write your CSS selectors within the media query. You’re doing it right if the selectors you’re writing are {between the media query brackets}, not outside them. 

* Correct selector placement:

  ```css 
  @media only screen and (max-width: 1000px) {
    // Your new CSS selectors go here
  }
  ``` 

* In your newly written media query, write a CSS selector that targets the `id` of `navigation`.

* In your CSS selector, give it the property `display` with a value of `none`. Write a CSS selector that targets the `class` of `icons`.

* Give the CSS selector the property `margin-left` with a value of `auto`.

* Write a `media query` that targets a screen size with the `max-width of 600px`.

* Write a CSS selector that targets the `id` of `headline`:

  * Give your selector the CSS property of `position` with a value of `static`.

  * Give your selector the CSS property of `margin` with a value of `20px`.

* Write a CSS selector that targets the `id` of `heroGrid`: 

  * Give your CSS selector the CSS property of `grid-template-areas`.

  * Rewrite the template areas so they display as follows:

    * “featuredProduct featuredProduct”
    * “secondaryProduct CTA”

  * This will cause our grid to restructure and display better on mobile devices.

* Write a CSS selector that targets the `id` of `categoryGrid`: 

  * Give your CSS selector the property of `grid-template-rows` with a value of `300px 300px 300px 300px 300px`. 

> **Note:** You need to create more rows in your grid for your content to occupy. In the previous grid’s template areas (Step 3, above), you have two rows. You will be creating five rows in your adjusted grid-template-areas.

* Give your CSS selector the property of `grid-template-columns` with a value of `1fr`.

* Give your CSS selector the CSS property of `grid-template-areas`.

* Rewrite the template areas, so they display as follows:

  * "Bookcases"

  * "Bedroom"

  * "Patio"

  * "Couches"
  
  * "Desks"

* Refresh the page. Check out your work!  

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
## index.html
```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
  <link href="https://fonts.googleapis.com/css?family=Poppins:100,200,300,400,500,600,700,800,900&display=swap" rel="stylesheet">
  <link href="css/style.css" rel="stylesheet" type="text/css">
  <title>Furniture Homepage</title>
</head>
<body>
  <nav id="navBar">
    <h1>Furniture</h1>
    <div id="navigation">
      <p class="highlight">New In</p>
      <p>Furniture</p>
      <p>Rest</p>
      <p>Decoration</p>
      <p>Outdoor</p>
      <p>Magazine</p>
      <p>Outlet</p>
    </div>
    <div class="icons">
      <img src="images/user.png">
      <img src="images/search.png">
      <img src="images/shopping-bag.png">
    </div>
  </nav>
  <section id="heroGrid">
    <div id="featuredProduct" class="heroGridArea">
      <div id="headline">
        <h3 id="newCollection">New Collection</h3>
        <h2>Chairs & Stools</h2>
        <p>Armchair upholstered in synthetic leather. Powder coated steel legs.</p>
      </div>
    </div>
    <div id="secondaryProduct" class="heroGridArea"></div>
    <div id="CTA" class="heroGridArea">
        <h4>Shop Now</h4>
        <img src="images/arrow-right.png">
      </div>
  </section>
  <div class="subHeading">
      <h3>Shop By Category</h3>
  </div>
  <section id="categoryGrid">
    <div id="bookcases" class="categoryGridArea">
      <div class="heading">Bookcases</div>
    </div>
    <div id="bedroom" class="categoryGridArea">
      <div class="heading">Bedroom</div>
    </div>
    <div id="couches" class="categoryGridArea">
      <div class="heading">Couches</div>
    </div>
    <div id="patio" class="categoryGridArea">
      <div class="heading">Patio</div>
    </div>
    <div id="desks" class="categoryGridArea">
      <div class="heading">Desks</div>
    </div>
  </section>
</body>
</html>
```

## style.css
```css
body {
  font-family: 'Poppins', sans-serif;
}

/* Grid CSS */

#heroGrid {
  margin: 0px 5%;
  display: grid;
  min-height: 500px;
  height: 70vh;
  grid-template-rows: 75% 25%;
  grid-template-columns: 75% 25%;
  grid-template-areas:
  "featuredProduct secondaryProduct"
  "featuredProduct CTA";
}

#featuredProduct {
  grid-area: featuredProduct;
  background-image: url("../images/furniture1.png");
}

#secondaryProduct {
  grid-area: secondaryProduct;
  background-image: url("../images/furniture2.png");
}

#CTA {
  grid-area: CTA;
  background-image: url("../images/woodbg.png");
  justify-content: space-around;
  cursor: pointer;
}

#headline {
  background-color: rgba(255,255,255,0.8);
  border-bottom: 5px solid #FF6200;
  position: absolute;
  right: -50px;
  top: 100px;
  padding: 25px;
  max-width: 550px;
  z-index: 100;
}

.heroGridArea {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  align-items: center;
  display: flex;
  position: relative;
}

/* Category Grid CSS */

.subHeading {
  text-align: center;
  border-bottom: 2px solid black;
  width: 300px;
  margin: 50px auto;
}

#categoryGrid {
  margin: 0px 5%;
  display: grid;
  grid-template-rows: 300px 300px 300px;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-areas:
  "bookcases bedroom patio"
  "couches couches patio"
  "desks desks desks"
  ;
}

#bookcases {
  grid-area: bookcases;
  background-image: url("../images/bookcases@2x.png");

}
#bedroom {
  grid-area: bedroom;
  background-image: url("../images/beds@2x.png");
}

#couches {
  grid-area: couches;
  background-image: url("../images/couch@2x.png");
}

#patio {
  grid-area: patio;
  background-image: url("../images/patio@2x.png");
}

#desks {
  grid-area: desks;
  background-image: url("../images/desks@2x.png");
}

.categoryGridArea {
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  margin: 5px;
  cursor: pointer;
  display: grid;
  align-content: end;
}

.heading {
  background-color: rgba(0,0,0,0.7);
  padding: 15px;
  height: 25px;
  color: white;
  font-size: 18px;
  border-bottom: 5px solid #FF6200;
}


/* Navigation CSS */
/* CHECK OUT THIS CODE BELOW IF YOU WANT TO GET A REFRESHER ON FLEX */

#navBar {
  display: flex;
  flex-direction: row;
  margin: 0px 5%;
}
#navBar h1 {
  width: 25%;
  font-weight: 500;
}
#navigation {
  display: flex;
  width: 50%;
  align-items: center;
  justify-content: space-evenly;
}
#navigation p {
  cursor: pointer;
  text-decoration: none;
}
.icons {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 25%;
}
.icons img {
  margin: 15px;
  cursor: pointer;
}
.highlight {
  color: #FF6200;
  font-weight: 700;
}

/* Typography CSS */

h2 {
  font-size: 60px;
  margin: 0px 0px;
  color: #FF6200;
}

h3 {
  font-size: 32px;
  font-weight: 300;
  margin: 0px 0px;
}

h4 {
  color: white;
  font-weight: 400;
  font-size: 22px;
}


#headline p {
  max-width: 350px;
  font-size: 16px;
  font-weight: 300;
  margin: 0px 0px;
  color: #636364;
}

@media only screen and (max-width: 1000px) {
  #navigation {
    display: none;
  }
  .icons {
    margin-left: auto;
  }
}

@media only screen and (max-width: 600px) {
  #headline {
    position: static;
    margin: 20px;
  }
  #heroGrid {
    grid-template-areas:
    "featuredProduct featuredProduct"
    "secondaryProduct CTA";
  }
  #categoryGrid {
    grid-template-rows: 300px 300px 300px 300px 300px;
    grid-template-columns: 1fr;
    grid-template-areas:
      "bookcases"
      "bedroom"
      "patio"
      "couches"
      "desks"
    ;
  }
}
```
{{% /expand%}}