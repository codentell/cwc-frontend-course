+++
title = "08. Project  Landing Page 👩‍🎓👨‍🎓"
weight = 8
tags = ["html"] 
+++


# Unit 01 Mini-Project: Landing Page

In this mini-project, you will build a landing page using HTML and CSS. While you will be responsible for your own landing page, you will work in a group to brainstorm and share ideas.

## Instructions

Work in your group to implement the following user stories:

* As a client, I want to view a single webpage that collects a visitor's contact information.

* As a client, I want the landing page to have a header and footer.

* As a client, I want the landing page to have an image with a caption.

* As a client, I want the landing page to have a contact form.

* As a client, I want the landing page to have a polished and accessible UI.

## Acceptance Criteria

* It's done when the page uses semantic HTML elements.

* It's done when the page uses universal, element, and class selectors in CSS.

* It's done when the page features at least three colors in the design.

* It's done when the page uses a single font and font family for all text.

* It's done when the page uses at least two heading elements (`<h1>` through `<h6>`).

* It's done when the header is fixed to the top of the page on scroll.

* It's done when the header contains a navigation bar with three links that display inline, including a contact link.

* It's done when, if the contact link is clicked, the page jumps directly to the contact form.

* It's done when the contact form includes `input` elements for name and email.

* It's done when the contact form includes a Send button.

* It's done when the image includes a descriptive `alt` attribute.

* It's done when the page is deployed to GitHub Pages.

## 💡 Notes

Follow these instructions to deploy your project to GitHub Pages:

1. Create a new repository on your GitHub account and clone it to your computer.

2. When you're ready to deploy, use the `git add`, `git commit`, and `git push` commands to save and push your code to your GitHub repository.

3. Navigate to your GitHub repository in the browser and then select the Settings tab on the right side of the page.

4. On the Settings page, select Pages on the left side of the page. On the GitHub Pages screen, choose `main` in the dropdown under Source.

5. Navigate to <your-github-username.github.io/your-repository-name> and you will find that your new webpage has gone live! For example, if your GitHub username is "lernantino" and the project is "css-demo-site", then your URL would be <lernantino.github.io/css-demo-site>.

You can also refer to this [YouTube video on enabling GitHub Pages](https://youtu.be/P4Mu1t5rIXg) for more guidance.

> **Important**: It might take a few minutes for GitHub pages to display your site correctly. If your project does not deploy or display correctly, check that all file paths in your application are relative and use the right casing. GitHub is case-sensitive, an inccorect capital or lowercase letter could cause problems in deployment.

## 💡 Hints

Refer to the documentation:

* [MDN Web Docs on HTML elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

* [MDN Web Docs on color](https://developer.mozilla.org/en-US/docs/Web/CSS/color)

* [MDN Web Docs on font](https://developer.mozilla.org/en-US/docs/Web/CSS/font)

* [MDN Web Docs on HTML section heading elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)

* [MDN Web Docs on how to structure a web form](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form)

* [MDN Web Docs on the button element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)

* [MDN Web Docs on the figure element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your group to further your knowledge:

* How can CSS be used to apply a different style to an `<a>` element when a cursor points at it?

Use [Google](https://www.google.com) or another search engine to research this.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
# index.html

```html
<!DOCTYPE html>
<html lang="en-GB">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" type="text/css" href="./assets/css/style.css">
  <title>My Landing Page</title>
</head>

<body>
  <header>
    <nav class="text-right">
      <ul>
        <li> <a href="https://github.com/">Github</a></li>
        <li> <a href="#">Portfolio</a></li>
        <li> <a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <h1 class="text-center">My New Website</h1>
    <figure>
      <img src="./assets/images/image-1.png" alt="Graphic with Coming Soon text">
      <figcaption class="text-center">Lorem ipsum dolor, sit amet consectetur adipisicing elit.</figcaption>
    </figure>
    <section id="contact">
      <h2 class="text-center">Contact Me</h2>
      <form>
        <ul>
          <li>
            <label class="text-right" for="name">Name:</label>
            <input type="text" id="name" name="user-name">
          </li>
          <li>
            <label class="text-right" for="email">Email:</label>
            <input type="text" id="email" name="user-email">
          </li>
        </ul>
        <div class="text-center">
          <button type="submit">SEND</button>
        </div>
      </form>
    </section>
  </main>

  <footer class="text-center">
    © 2022 My New Website Productions 
  </footer>
    
</body>
</html>
```

# style.css
```css
/* Universal Selector */
* {
  margin:0;
  padding:0;  
}

/* Element Selectors */
body {
  position: relative;
  font-family: "Goudy Bookletter 1911", sans-serif;
  font-size: 20px;
  background-color: #FDF8F5;
  color: #4F4846;
}

h1,
h2 {
  margin: 20px;
}

main {
  padding: 60px 0;
}

li {
  display: inline;
  padding: 0px 20px;
  text-decoration: none;
}

a {
  text-decoration: none;
  color: #FDF8F5;
}

header,
footer {
  height: 60px;
  width: 100%;
  line-height: 60px;
  background-color: #266150;
}

header {
  position: fixed;
  border-bottom: 10px solid #DDAF94;
}

footer {
  position: absolute;
  margin-top: 0;
  bottom: 0;
  border-bottom: 10px solid #4F4846;
  color: #FDF8F5;    
}

figure {
  margin-bottom: 40px;
}

img {
  display: block;
  margin: 20px auto;
}

section {
  margin-bottom: 0;
  padding: 20px 10px 40px 10px;
  border-top: 3px solid #DDAF94;
  background-color:  #E8CEBF;
}

form {
  /* Center the form on the page */
  margin: 0 auto;
  width: 500px;
  padding: 10px;
  border: 5px solid #DDAF94;
  border-radius: 20px;
}

label {
  display: inline-block;
  width: 100px;
}
  
input, 
textarea {
  box-sizing: border-box;
  width: 300px;
  border: 1px solid #4F4846;
}

textarea {
  vertical-align: top;
  height: 60px;
}
  
button {
  height: 40px;
  width: 120px;
  background-color: #4F4846;
  color: #FDF8F5;
}
 
/* Class Selectors */
.text-center {
  text-align: center;
}

.text-right {
  text-align: right;
}


```

{{% /expand%}}