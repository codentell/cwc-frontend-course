+++
title = "03. Subclasses 👩‍🏫🧑‍🏫"
weight = 3
tags = ["oop"] 
+++

### rectangle.js
```js
const Shape = require("./shape");

class Rectangle extends Shape {
  constructor(sideA, sideB) {
    const area = sideA * sideB;
    const perimeter = sideA * 2 + sideB * 2;

    super(area, perimeter);
    this.sideA = sideA;
    this.sideB = sideB;
  }
}

const rectangle = new Rectangle(12, 9);
rectangle.printInfo();
```

### shape.js

```js
class Shape {
  constructor(area, perimeter) {
    this.area = area;
    this.perimeter = perimeter;
  }

  printInfo() {
    for (const key in this) {
      console.log(`${key}: ${this[key]}`);
    }
  }
}

module.exports = Shape;
```