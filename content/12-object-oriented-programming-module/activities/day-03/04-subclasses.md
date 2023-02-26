+++
title = "04. Subclasses 👩‍🎓👨‍🎓"
weight = 4
tags = ["oop"] 
+++

# SubClasses

In this activity, we will extend basic vehicle classes with additional functionality. 

## Instructions

* Open [vehicle.js](starter/vehicle.js) and take a moment to familiarize yourself with the Vehicle class.

  * All vehicles have `id`, `numberOfWheels`, and `sound` properties. `printInfo` prints the id and number of wheels on the vehicle.

* Create a `Car` class that extends the `Vehicle` class. The car should have the following features:
  * A `color` property.
  * A passengers property.
  * A `checkPassengers()` method that checks to see if there are four or fewer passengers. If not, `console.log` that there are too many passengers.
  * A `useHorn` method that prints the car's sound to the console.

* Create a `Boat` class that also extends the `Vehicle` class. The boat should have the following features:
  * A crew property.
  * A `crewSoundOff()` method that prints each member of the crew to the console.
  * A `useHorn` method that prints the boat's sound to the console.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### boat.js
```js
const Vehicle = require("./vehicle");

class Boat extends Vehicle {
  constructor(id, type, crew) {
    super(id, 0, "bwom");
    this.type = type;
    this.crew = crew;
  }
  useHorn() {
    console.log(this.sound);
  }
  crewSoundOff() {
    this.crew.forEach(member => {
      console.log(`${member.name} reporting for duty!`);
    });
  }
}

const boatPassengers = [
  {
    name: "Blackbeard"
  },
  {
    name: "Mary Read"
  },
  {
    name: "Henry Morgan"
  },
  {
    name: "Madame Cheng"
  }
];

const boat = new Boat(16, "sailboat", boatPassengers);

console.log("---BOAT---");
boat.printInfo();
boat.useHorn();
boat.crewSoundOff();

```

### car.js
```js
const Vehicle = require("./vehicle");

class Car extends Vehicle {
  constructor(id, color, passengers) {
    super(id, 4, "beep");
    this.color = color;
    this.passengers = passengers;
  }

  useHorn() {
    console.log(this.sound);
  }

  checkPassengerLength() {
    if (this.passengers.length > 4) {
      console.log("Cars only seat 4 people. You have too many passengers!");
    } else {
      console.log(`You have room for ${4 - this.passengers.length} people.`);
    }
  }
}

const carPassengers = [
  {
    name: "Aristotle"
  },
  {
    name: "Confucius"
  },
  {
    name: "Socrates"
  },
  {
    name: "Lao-Tzu"
  },
  {
    name: "Plato"
  }
];

const car = new Car(15, "blue", carPassengers);

console.log("---CAR---");
car.printInfo();
car.useHorn();
car.checkPassengerLength();
```

### vehicle.js
```js
class Vehicle {
  constructor(id, numberOfWheels, sound) {
    this.id = id;
    this.numberOfWheels = numberOfWheels;
    this.sound = sound;
  }

  printInfo() {
    console.log(`This vehicle has ${this.numberOfWheels} wheels`);
    console.log(`This vehicle has an id of ${this.id}`);
  }
}
module.exports = Vehicle;
```
{{% /expand%}}