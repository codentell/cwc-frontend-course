+++
title = "03. Basic CSS 👩‍🏫🧑‍🏫"
weight = 3
tags = ["html"] 
+++

```html
<!DOCTYPE html>
<html lang="en-us">

<head>
  <meta charset="UTF-8">
  <title>Basic CSS Example</title>

  <!-- Introducing the Style Tag! -->
  <!-- ========================== -->

  <!-- Now you can customize the look of your sites. Each rule in the style tag changes the appearance of its associated element (notice how each rule names an element from the HTML body). -->
  <style>
    /*
			NOTE: Commenting is a bit different in CSS. 
		  They start with forward-slash + asterisk 
		  and end with back-slash + asterisk.
		  */
    /* h1 heading tag */
    
    h1 {
      /* Put a 15-pixel margin at the bottom of the heading. */
      margin-bottom: 15px;
      /* Change the size of your font to 60 pixels high. */
      font-size: 60px;
      /* This will color the heading font white. */
      color: white;
      /* Align the text to the center of its enclosing element (e.g. div). */
      text-align: center;
      /* Underline the text. */
      text-decoration: underline;
      /* The background of the heading element will now be black. */
      background-color: black;
    }
    /* h2 heading tags */
    
    h2 {
      /* Put a 15-pixel margin at the top of all h2 headings. */
      margin-top: 15px;
      margin-bottom: 15px;
      font-size: 40px;
      text-align: center;
    }
    /* h3 heading tags */
    
    h3 {
      margin-top: 15px;
      font-size: 20px;
      text-align: center;
    }
    /* All img tags */
    
    img {
      /* 
				Center a block element in the middle of its enclosing tag.
				When you use the "auto" rule on both left and right margins, 
				your browser will do the math necessary to center a block element.
				*/
      margin-left: auto;
      margin-right: auto;
      /* Block display (more on this later) */
      display: block;
    }
    /* All p tags */
    
    p {
      text-align: center;
      font-size: 20px;
      /* Bold the text. */
      font-weight: bold;
    }
    /* All unordered list tags */
    
    ul {
      text-align: center;
      font-size: 35px;
      /* Give an element a solid border. */
      border-style: solid;
      /* Render the border 5 pixels thick. */
      border-width: 5px;
      /* Include bullets in the content flow. */
      /* More info here: http://www.w3schools.com/cssref/pr_list-style-position.asp */
      list-style-position: inside;
    }
  </style>
</head>

<body>

  <h1>Awesome Header</h1>
  <h2>Smaller Awesome Header</h2>
  <h3>Even Smaller Header</h3>

  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem consequatur unde aut dolores odio hic, accusamus recusandae ipsam illum enim voluptatibus obcaecati totam tempora eum quod sapiente. Corporis, quidem, culpa?</p>
  <img src="https://pbs.twimg.com/media/BsgYfMQCQAAWVKH.jpg" alt="Awesome" width="25%">

  <h3>Menu Links</h3>
  <ul>
    <li><a href="https://www.google.com">Google</a></li>
    <li><a href="https://www.facebook.com">Facebook</a></li>
    <li><a href="https://www.twitter.com">Twitter</a></li>
  </ul>

</body>

</html>



```


### Notes 📖: 

# Why !?
## Pros of CSS

1. CSS helps to create a consistent and professional look and feel to webpages, making them more aesthetically pleasing.

2. CSS allows web designers to separate the content from the presentation, meaning you can easily make changes to the styling of a page without having to rework the HTML.

3. CSS is relatively easy to learn and use, making it a great tool for web designers of any skill level.

4. CSS is compatible across multiple browsers, so you don’t have to worry about your design looking different on one browser versus another.

## Cons of CSS:

1. CSS can be difficult to debug if there are any issues with the code.

2. CSS is not always fully supported in older browsers, which can lead to compatibility issues.

3. CSS can be time consuming to write and maintain, especially for complex designs.

4. CSS is not always intuitive, and can require a lot of trial and error to get it right.