+++
title = "03. Scope 👩‍🏫🧑‍🏫"
weight = 3
tags = ["third party apis"] 
+++

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Scope Activity #1</title>
</head>
<body>
  <h1>Scope Activity #1</h1>
  <h2>✨Open the console to see the magic!✨</h2>

  <script>

    function outside() {
      // what is the scope of this variable?
      var x = 1;

      // what is the scope of this function and the scope of y?
      function inside(y) {

        console.log(x + y);
      }

      return inside;
    }

    // what is happening here?
    var insideOut = outside();

    // What does this return?
    insideOut(2);

    // Uncaught ReferenceError: x is not defined.
    // How does insideOut have access to x?
    console.log("The value of 'x' outside 'outside()' is: " + x);

  </script>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Closure</title>
</head>
<body>
  <h2>Check console to see the madness!</h2>

  <script>
    var cat = {
      name: "Gus",
      color: "gray",
      age: 15,

      printInfo: function() {
        console.log("inside printInfo()");

        // What will this print?
        console.log(this);

        // What will this print?
        console.log("Name:", this.name, "Color:", this.color, "Age:", this.age);

        var nestedFunction = function() {
          console.log("inside nestedFunction()");

          // What will this print?
          console.log(this);

          // What will this print?
          console.log("Name:", this.name, "Color:", this.color, "Age:", this.age);
        };

        nestedFunction();
      }
    };

    // calls the printInfo function. Which subsequently calls the nestedFunction()
    cat.printInfo();

</script>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Lexical Scope</title>
</head>
<body>

  <h2>Let's Talk About Scope!</h2>

  <script type="text/javascript">

    // Example One: Global Scope
    // -------------------------------------------
    var a = 1;
    function one() {
      alert("One: " + a);
    }

    // What will get alerted?
    one();

    // Example Two: Local Scope
    // -------------------------------------------
    function twotop() {

      function two(a) {
        alert("Two: " + a);
      }

      two(a);
    }

    // What will get alerted?
    twotop();

    // Example Three: Local Scope
    // -------------------------------------------
    var a = 5;
    function three() {

      var a = 3;
      alert("Three: " + a);
    }

    // What will get alerted?
    three();

    // Example Four: Local Scope
    // -------------------------------------------
    function first() {
      var a = 5;

      function second() {
        var a = 3;

        function third() {
          alert("Four: " + a);
        }

        third();
      }

      second();

      alert("Five: " + a);
    }

    // What will get alerted?
    first();

  </script>
</body>
</html>
```