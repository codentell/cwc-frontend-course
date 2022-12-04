+++
title = "01. Relative Paths 👩‍🎓👨‍🎓"
weight = 1
tags = ["html"] 
+++

# Relative File Paths

## Instructions

* Then modify each of the four `html-bio.html` pages such that they can access the CSS inside their folder. Don't move the CSS file and don't move the HTML file. 

* Use relative linking to make it work!

* **Hint:** If you need some reading material on relative linking, you can use <https://css-tricks.com/quick-reminder-about-file-paths/>.

* If you finish early, help out those around you, or begin reading through the Learn CSS Layout Guide found here: <http://learnlayout.com/no-layout.html>.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
## Demo html-bio-with-css.html Solution
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>CSS Stylesheets With Relative Paths</title>

  <!-- This line is money! It points your HTML to the CSS file. -->
  <link rel="stylesheet" type="text/css" href="style.css">
  <!-- Notice the "relative" pathway? It matches a file inside our current directory's "assets" folder. Open it to see our style rules. -->
</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```
## RelativePaths_1 Solution
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Relative Paths Assignment 1</title>

  <!-- Fill in the href to the CSS such that this HTML file can access the CSS -->
  <!-- Don't move the HTML or CSS file. Use Relative Linking -->
  <link rel="stylesheet" type="text/css" href="style.css">
</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```

## RelativePaths_2 Solution
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Relative Paths Assignment 2</title>

  <!-- Fill in the href to the CSS such that this HTML file can access the CSS -->
  <!-- Don't move the HTML or CSS file. Use Relative Linking -->
  <link rel="stylesheet" type="text/css" href="assets/style.css">
</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```


## RelativePaths_3 Solution
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Relative Paths Assignment 3</title>

  <!-- Fill in the href to the CSS such that this HTML file can access the CSS -->
  <!-- Don't move the HTML or CSS file. Use Relative Linking -->
  <link rel="stylesheet" type="text/css" href="assets/style/style.css">
</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```

## RelativePaths_4 Solution
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Relative Paths Assignment 4</title>

  <!-- Fill in the href to the CSS such that this HTML file can access the CSS -->
  <!-- Don't move the HTML or CSS file. Use Relative Linking -->
  <link rel="stylesheet" type="text/css" href="../style.css">
</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```

## RelativePaths_WorkingExample Solution
```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>1.2.9 Exercise</title>

  <!-- This line is money! It points your HTML to the CSS file. -->
  <link rel="stylesheet" type="text/css" href="assets/style.css">
  <!-- Notice the "relative" pathway? It matches a file inside our current directory's "assets" folder. Open it to see our style rules. -->
</head>

<body>
  <header>
    <h1>Student Bio</h1>
  </header>

  <div class="container">

    <section id="main-bio">

      <h2>Your Name</h2>

      <img id="bio-image" src="https://placehold.it/200x200" alt="Your Name">

      <p>Write a short paragraph or two about yourself, or use placeholder text from <a href="http://www.lipsum.com/">www.lipsum.com</a></p>
    </section>

    <section id="contact-info">
      <h2>Contact Info</h2>
      <ul>
        <li><strong>Email:</strong> <a href="#">someplace@gmail.com</a></li>
        <li><strong>Github:</strong> <a href="#">sampleName</a></li>
        <li><strong>Portfolio:</strong> <a href="#">coming soon</a></li>
      </ul>
    </section>
  </div>

</body>

</html>
```
{{% /expand%}}

