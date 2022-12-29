+++
title = "01. Intro Functions 👩‍🏫🧑‍🏫"
weight = 1
tags = ["advanced javascript"] 
+++

### functions 

```js
// Various Arrays
var brands = ["Acer", "Apple", "Sony", "Samsung"];
var heroes = ["Black Panther", "Cyborg", "Black Canary", "Donna Troy", "Huntress", "Blue Beetle", "Captain Atom"];
var booksOnMyShelf = ["Calculus Early Transcendentals", "Ravens", "The Self Illusion", "Harry Potter"];
var thingsInFrontOfMe = ["Laptop", "Beanbag", "Cats", "Slippers"];
var howIFeel = ["Sleep Deprived", "Wired on Coffee", "Excited"];

// FUNCTIONS
// ========================================================================================

// Here we create a "Function" that allows us to "call" (run) the loop for any array we wish.
// We pass in an array as an "argument".
function consoleInside(arr) {

  // We then loop through the selected array.
  for (var i = 0; i < arr.length; i++) {

    // Each time we print the value inside the array.
    console.log(arr[i]);
  }
  console.log("---------");
}


// FUNCTION CALLS (Execution)
// =======================================================================================

// Here we call the function to run our for-loop code on each of the following arrays.
consoleInside(brands);
consoleInside(heroes);
consoleInside(booksOnMyShelf);
consoleInside(thingsInFrontOfMe);
consoleInside(howIFeel);
```

### no-functions

```js
// Various Arrays
 var brands = ["Acer", "Apple", "Sony", "Samsung"];
 var heroes = ["Black Panther", "Cyborg", "Black Canary", "Donna Troy", "Huntress", "Blue Beetle", "Captain Atom"];
 var booksOnMyShelf = ["Calculus Early Transcendentals", "Ravens", "The Self Illusion", "Harry Potter"];
 var thingsInFrontOfMe = ["Laptop", "Beanbag", "Cats", "Slippers"];
 var howIFeel = ["Sleep Deprived", "Wired on Coffee", "Excited"];

 // For Loop for Brands
 for (var i = 0; i < brands.length; i++) {
   console.log(brands[i]);
 }
 console.log("---------");

 // For Loop for Heroes
 for (var j = 0; j < heroes.length; j++) {
   console.log(heroes[j]);
 }
 console.log("---------");

 // For Loop for booksOnMyShelf
 for (var k = 0; k < booksOnMyShelf.length; k++) {
   console.log(booksOnMyShelf[k]);
 }
 console.log("---------");

 // For Loop for thingsInFrontOfMe
 for (var l = 0; l < thingsInFrontOfMe.length; l++) {
   console.log(thingsInFrontOfMe[l]);
 }
 console.log("---------");

 // For Loop for howIFeel
 for (var m = 0; m < howIFeel.length; m++) {
   console.log(howIFeel[m]);
 }
 console.log("---------");
```