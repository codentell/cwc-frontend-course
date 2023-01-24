

# Bujumbura

## Instructions

* Using the starter code add in the missing code necessary to accomplish the following:

  * Query the [OpenWeatherMap API](http://openweathermap.org/api) for the current weather data on Bujumbura, Burundi.

  * Log the retrieved data from this query to console.

  * Parse the retrieved data to display wind speed, humidity, and temperature information into the HTML.

## 💡 Hint

You will need to request an API key from the website.

## 🏆 BONUS

If you have completed the activity and want to further your knowledge, work through the following challenge:

How to convert the Kelvin temperature provided into Celsius.

---



```html
<!DOCTYPE html>
<html lang="en-gb">

<head>
  <meta charset="utf-8">
  <title>Bujumbura Data</title>
</head>

<body>
  <!-- Retrieved data will be dumped here -->
  <div class="city"></div>
  <div class="wind"></div>
  <div class="humidity"></div>
  <div class="temp"></div>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script type="text/javascript" src="./script.js"></script>
</body>

</html>
```


```js
// This is our API key
var APIKey = "166a433c57516f51dfab1f7edaed8413";

// Here we are building the URL we need to query the database
var queryURL = "https://api.openweathermap.org/data/2.5/weather?" +
  "q=Bujumbura,Burundi&appid=" + APIKey;

// Here we run our AJAX call to the OpenWeatherMap API
$.ajax({
  url: queryURL,
  method: "GET"
})
  // We store all of the retrieved data inside of an object called "response"
  .then(function(response) {

    // Log the queryURL
    console.log(queryURL);

    // Log the resulting object
    console.log(response);

    // Transfer content to HTML
    $(".city").html("<h1>" + response.name + " Weather Details</h1>");
    $(".wind").text("Wind Speed: " + response.wind.speed);
    $(".humidity").text("Humidity: " + response.main.humidity);
    
    // Convert the temp to Celsius
    var tempC = response.main.temp - 273.15;

    // add temp content to html
    $(".temp").text("Temperature (K) " + response.main.temp);
    $(".tempC").text("Temperature (C) " + tempC.toFixed(2));

    // Log the data in the console as well
    console.log("Wind Speed: " + response.wind.speed);
    console.log("Humidity: " + response.main.humidity);
    console.log("Temperature (C): " + tempC);
  });
```