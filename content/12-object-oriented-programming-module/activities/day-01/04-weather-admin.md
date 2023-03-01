+++
title = "04. Weather Admin 👩‍🎓👨‍🎓"
weight = 4
tags = ["oop"] 
+++

# Weather Admin

In this activity, you will audit a CLI-based weather application that will give updates about the weather at the searched location.

## Instructions

* There are two ways to run this app: as a user or as an administrator. To run as an administrator, type `node CLI.js admin` To run as a user, type `node CLI.js user bob "los angeles, ca"`, where the user mode must provide a name and a location as additional arguments.

* Ideally, users can search for weather data about a location. Every time they search, the place and time get saved to a text file. So when the app is run as an administrator, the admin user can see a history of all searches.

* Unfortunately, this app is also **broken**. Try to run it as either a user or administrator and fix the actual errors that appear in the console and then any "logic" errors that prevent the expected behavior.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### CLI.js
```js
const WeatherAdmin = require('./WeatherAdmin');

// Hold the value whether someone is an "admin" or "user"
const loginType = process.argv[2];

// If they are a user... they will also need to provide a "name"
const userName = process.argv[3];

// And they will need to provide a "location"
const userLocation = process.argv[4];

// Create an instance of the WeatherAdmin. Remember WeatherAdmin is a constructor! Not an object.
const myAdmin = new WeatherAdmin();

if (loginType === 'admin') {
  myAdmin.getData();
} else {
  myAdmin.newUserSearch(userName, userLocation);
}
```
### UserSearch.js
```js
// We're incorporating an npm package for doing weather searches.
const weather = require('weather-js');

// Creates a UserSearch Constructor
const UserSearch = function (name, location) {
  this.name = name;
  this.location = location;
  this.date = Date.now();

  this.getWeather = () => {
    weather.find({ search: this.location, degreeType: 'C' }, (err, result) => {
      if (err) {
        console.log(err);
      }
      console.log(JSON.stringify(result, null, 2));
    });
  };
};

module.exports = UserSearch;
```

### WeatherAdmin.js
```js
const fs = require('fs');
const moment = require('moment');
const UserSearch = require('./UserSearch');

const WeatherAdmin = function () {
  this.getData = () => {
    fs.readFile('log.txt', 'utf8', (error, data) => {
      console.log(data);
    });
  };

  this.newUserSearch = (name, location) => {
    const newUserSearch = new UserSearch(name, location);
    const logTxt = `\nName: ${newUserSearch.name} Location: ${
      newUserSearch.location
    } Date: ${moment(newUserSearch.date).format('DD/MM/YYYY')}`;

    fs.appendFile('log.txt', logTxt, (err) => {
      if (err) throw err;
    });

    newUserSearch.getWeather();
  };
};

module.exports = WeatherAdmin;

```

{{% /expand%}}