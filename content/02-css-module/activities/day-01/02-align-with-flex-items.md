+++
title = "02. Align With Flex Items 👩‍🎓👨‍🎓"
weight = 2
tags = ["css"] 
+++


# Aligning Flex Items

In this activity, you’ll practice aligning CSS Flexbox items inside parent containers.

## Instructions

* Open the file `index.html`.

  * This file includes parent containers with child elements. 

* When you open it in your browser, take notice of what it’s missing. 

  * **Hint:** None of the flex children are aligned inside their container. 

* Open the `index.css` file and add the `align-items property` to the `.alignItems` selector.

* Set the value for `align-items` property to center. 

* Save your files and refresh `index.html` in your browser.

* Change the value for `align-items` to `flex-end` or `flex-start` to see the differences that each value creates.

* Add the `justify-content` property to the `.justifyContent` selector.

  * Try out the different values listed here and see what they do to your content.

* Lastly, add properties to the `.perfectlyCentered` selector to center the child element.

  * **Hint:** You will need to use both `align-items` and `justify-content`.

* Your finished design should look like the image below:

  ![Aligning Flex Items Solution](../images/aligning-flex-items-solution.png)

* Resources: If you get stuck, google `align-items` and `justify-content`. 

---

## Folder Structure
```bash
02-Stu-Aligning-With-Flex-Items
├── css
│    └── index.css     
└── index.html
```


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

# index.html

```html
<!DOCTYPE html>
<html lang="en-gb">
<head>
  <link href="css/index.css" type="text/css" rel="stylesheet">
</head>
<body>
  <section class="alignItems flexContainer">
    <div class="flexItem">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </div>
    <div class="flexItem">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </div>
    <div class="flexItem">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </div>
  </section>
  <section class="justifyContent flexContainer">
    <div class="flexItem">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </div>
    <div class="flexItem">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </div>
    <div class="flexItem">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </div>
  </section>
    <section class="perfectlyCentered flexContainer">
      <div class="flexItem">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    </section>
  </div>
</body>
</html>


```

# index.css

```css
.flexItem {
  background-color: lightyellow;
  margin: 10px;
  padding: 10px;
  width: 250px;
  height: 250px;
}
.flexContainer {
  display: flex;
  height: 400px;
  background-color: lightblue;
  margin: 10px;
  padding: 10px;
}
.justifyContent {
  justify-content: center;
}
.perfectlyCentered {
  justify-content: center;
  align-items: center;
}
.alignItems {
  align-items: center;
}
```


{{% /expand%}}