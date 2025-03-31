

## Tool: **JSON APIs**

## Project: **Dress based on the weather app**

---

### 10/19/24:
*  Understand JSON Basics and APIs
   * What is JSON? JSON (JavaScript Object Notation) is a lightweight data interchange format that's easy for humans to read and write, and easy for machines to parse and generate.
   * What is an API?: An Application Programming Interface (API) allows different software applications to communicate with each other.
* Read this blog of [designing and implementing a weather data API](https://www.tinybird.co/blog-posts/designing-and-implementing-a-weather-data-api).
* Watched this 30 minutes video [Weather App (JSON data download via API) - WeatherAPI.com](https://www.youtube.com/watch?v=QY8KvyzZUQ4)
* Watched this tutorial [Weather API Project Tutorial using HTML, CSS, and JavaScript | For Beginners](https://www.youtube.com/watch?v=JubKY5p3qRc)
* [W3shools tutorials ](https://www.w3schools.com/js/js_json_intro.asp)
   * Completed tutorials.
* [Read this article](https://weatherstack.com/free-weather-api-no-key#:~:text=Among%20the%20free%20Weather%20APIs,need%20for%20an%20API%20key.)
  * Talks about the best free weather APIs that don't require a key
* Next steps
   *  Continue learning about JSON APIs



### 10/17/24:
* Tried make something to show the weather in jsbin using Open-Meteo APIs
   * [Weather](ny-weather.png)
   * [Open-Meteo Weather Forecast API](https://open-meteo.com/en/docs#latitude=40.7143&longitude=-74.006&current=temperature_2m&forecast_days=1)
* However its still using latitude and longitude
* Watched this turtorial [Weather App using Open Weather API | Recharts | Open-Meteo API](https://www.youtube.com/watch?v=LHAAT9cnQlY)


* Next steps
   *  Search more about using zip code rather than latitude and longitude

### 11/4/2024  - 11/11/2024
* [Open Meteo](https://open-meteo.com/)
    * The official documentation for the Open Meteo API, with detailed information on how to make requests for weather data, including temperature, wind, precipitation, etc.
    * Helps understand how to request data
* Open Meteo API Endpoint:

   `https://api.open-meteo.com/v1/forecast?latitude={lat}&longitude={lon}&current_weather=true`

     * latitude: Latitude of the location.
     * longitude: Longitude of the location.
     * current_weather=true: This tells the API to return current weather data.
* For example:
   * To get current weather for New York:

`https://api.open-meteo.com/v1/forecast?latitude=40.7128&longitude=-74.0060&current_weather=true`
* [Open Meteo GitHub Repository](https://github.com/Open-Meteo)
    * Here you can find the source code, examples, and additional resources related to the Open Meteo API.
* Learn JSON with JavaScript (How to parse JSON)
     * [MDN JSON Guide](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON)
     * This guide explains how JSON works and how you can analyze JSON data, which is key for handling responses from APIs like Open Meteo.
* [JavaScript Fetch API](https://www.youtube.com/watch?v=Oive66jrwBs)
     * This tutorial covers the basics of the Fetch API in JavaScript. This is essential for understanding how to interact with external APIs like Open Meteo.
* Next steps
   *  Try to build something with Open Metro APIs
 
### 11/18/24 - 11/24/24
* [Add icons to represent each weather](https://github.com/open-meteo/open-meteo/issues/789)
    * I could use this to add icons based on weather
 
Background Changes Based on Weather: Change the background of your app based on the weather (e.g., a sunny background for clear weather, dark clouds for rainy weather). You can use CSS to change background images dynamically.

```js
Copy code
if (weatherCondition === "Clear") {
  document.body.style.backgroundImage = "url('sunny.jpg')";
} else if (weatherCondition === "Rainy") {
  document.body.style.backgroundImage = "url('rainy.jpg')";
}
```
* Currently, I am using latitude and longitude to get weather data, but to switch to zip codes to make it easier for users to input locations. I need to check API Documentation: Some APIs, like OpenWeatherMap, accept zip codes directly in their request URL. For example, you could make a request like:

`https://api.openweathermap.org/data/2.5/weather?zip=94040,us&appid=YOUR_API_KEY`

* For Open-Meteo: Open-Meteo primarily uses latitude and longitude for location. If you still want to use zip codes, you might need a geocoding service (like Geocoding API or Nominatim), which converts zip codes or addresses to latitude and longitude, then use the latitude/longitude with the Open-Meteo API.
* Example using Nominatim (OpenStreetMap's API):

 `https://nominatim.openstreetmap.org/search?postalcode=94040&country=USA&format=json 
 `

 *  This will return latitude and longitude that you can then pass to Open-Meteo.
 *  Hourly Weather Forecasts: If your API supports it, you can display the weather forecast for the upcoming hours. For example, Open-Meteo provides forecasts for the next 24 hours.Example API Call for Hourly Data:

`https://api.open-meteo.com/v1/forecast?latitude=40.7128&longitude=-74.0060&hourly=temperature_2m,p`

* [Forecasting weather with Open-Meteo API](https://medium.com/@owmo13/forecasting-weather-with-open-meteo-api-using-jetpack-compose-7e58387f10e1)
    * Example of weather app using JSON APIs
* [Geolocation in Weather App](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API/Using_the_Geolocation_API)
    * Adding Geolocation to Your Weather App – This tutorial shows how to use the browser's geolocation API to get the user's current location and display the weather for that location.
* Units of Measurement
    * Some users may prefer different units, like temperature in Celsius or Fahrenheit. I need to sure my app supports unit conversion (e.g., Celsius to Fahrenheit or meters per second to miles per hour). OpenWeatherMap and other APIs support units like:
         * metric (Celsius, meters per second)
         * imperial (Fahrenheit, miles per hour)

* Next steps
    * Try to build something with Open Metro APIs

### 12/2/24 - 12/8/24
Tinkered by making a simple weather-based dressing app using HTML, CSS, JavaScript arrays, functions, conditions, and loops. 
   *   [This is the link to my simple weather-based dressing app](https://github.com/kostelal0688/sep11-freedom-project/blob/main/tool/tinkering)
* **How I made it:**
* HTML : The page includes a title, radio buttons for Celsius and Fahrenheit selection, and a container to display the weather information `(<div id="weather-info"></div>)`.
JavaScript:
* Array of Cities: The cities array holds multiple cities with their latitude and longitude.
* Toggle Functionality: The radio buttons (Celsius and Fahrenheit) allow the user to toggle between temperature units.  
* Fetch Weather Data: The getWeather() function makes API calls to Open Meteo to fetch current weather for each city.
* Temperature Conversion: The temperature is either in Celsius or Fahrenheit, depending on the user’s choice. The conversion between Celsius and Fahrenheit is handled by a simple formula.
* Clothing Suggestion: The suggestClothing() function takes the temperature and returns an appropriate clothing suggestion based on conditions (if, else).
* Functions:
    * getWeather(): Fetches weather data for all cities using a loop and displays it.
    * suggestClothing(): Takes a temperature and returns a clothing suggestion using conditional statements.
* Loops:
    * The forEach() method is used to loop through each city in the cities array and fetch its weather.
    * The result for each city is dynamically inserted into the weather-info container.
* **How It Works:**
    * Weather Fetching: The getWeather() function fetches weather data for the cities from the Open Meteo API.
    * Unit Conversion: The user can toggle between Celsius and Fahrenheit, which automatically converts the temperature in the app.
### 12/16/24 - 1/2/25
 * Continued improving my weather-based dressing app using HTML, CSS, and JavaScript.
 * Improved functionality by incorporating weather icons to visually represent weather conditions (sunny, cloudy, rainy, etc.).
* Key Improvements:
    * Weather Icons:
    * Integrated weather icons based on conditions fetched from the API. For instance, if the weather is "Clear", it shows a sun icon, "Rainy" shows a rain cloud, and so on.I used the weather condition data (like "Clear", "Rain", etc.) from the Open-Meteo API to assign icons.
Example:
```js
if (weatherCondition === "Clear") {
    document.body.style.backgroundImage = "url('sunny.jpg')";
    weatherIcon.src = "sun-icon.png";  // Example for icon
} else if (weatherCondition === "Rain") {
    document.body.style.backgroundImage = "url('rainy.jpg')";
    weatherIcon.src = "rain-icon.png";
}
```
* Geolocation API Integration
* [Using the Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API/Using_the_Geolocation_API)
    * Read this article
    * Geolocation Feature: Integrate the ability for the app to automatically detect the user's location and show the weather for that location. This would require using the browser's Geolocation API.
 * [Geolocation](https://www.w3.org/TR/geolocation/)
    * Read this article about specifications and guidelines for implementing Geolocation API in your app.

```js
if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(function(position) {
        let lat = position.coords.latitude;
        let lon = position.coords.longitude;
        // Use lat and lon in the API call
    });
} else {
    alert("Geolocation is not supported by this browser.");
}
```
* Open-Meteo is a great way to fetch weather data based on latitude and longitude. You can combine this with the Geolocation API to automatically detect the user's location and provide real-time weather for that location.

   * Here’s how you can use the Geolocation API in the browser to get the user's current location and then use that information to fetch weather data:

```js
if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(function(position) {
        let lat = position.coords.latitude;
        let lon = position.coords.longitude;
        
        // Construct the Open-Meteo API URL with the user's location
        const url = `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current_weather=true`;
        
        fetch(url)
            .then(response => response.json())
            .then(data => {
                const temp = data.current_weather.temperature;
                const condition = data.current_weather.weathercode;
                let weatherDescription = '';

                // Map the weather code to actual conditions
                if (condition === 0) weatherDescription = 'Clear';
                else if (condition === 1) weatherDescription = 'Partly Cloudy';
                else if (condition === 2) weatherDescription = 'Cloudy';
                else if (condition === 3) weatherDescription = 'Rainy';
                
                console.log(`Temperature: ${temp}°C, Condition: ${weatherDescription}`);
            })
            .catch(error => console.log('Error fetching data:', error));
    });
} else {
    console.log("Geolocation is not supported by this browser.");
}
```

This feature will enable your app to provide users with weather data for their exact location without needing them to input coordinates.
* Next steps
   * Try to build something with Geoloction.

 ### 1/6/25 - 1/13/25
* Integrated Zip Code Input:
   * Implemented a feature allowing users to input a zip code. The zip code is converted into latitude and longitude using the Nominatim API and passed into the Open-Meteo API to fetch the weather data.
    * [Nominatim API](https://nominatim.org/release-docs/3.6/develop/Postcodes/)
* Step-by-Step Process:
  1. User Input (Zip Code): The user enters a zip code into a form field on the web page.
  2. Convert Zip Code to Coordinates:
     * The zip code is sent to the Nominatim API, which returns the corresponding latitude and longitude of that zip code. Nominatim is an open-source geocoding tool that converts addresses or postal codes to geographic coordinates.
     * Example API call:
`https://nominatim.openstreetmap.org/search?postalcode=94040&country=USA&format=json`
     * This request returns a JSON response with information such as:
```js
 [
  {
    "lat": "37.3861",
    "lon": "-122.0838",
    "display_name": "Mountain View, California, USA"
  }
]
```
3. Fetch Weather Data:
      * Using the coordinates from Nominatim, the app constructs an API request to the Open-Meteo API to retrieve the weather data for the location.
Example Open-Meteo API call using the coordinates (latitude: 37.3861, longitude: -122.0838):
`https://api.open-meteo.com/v1/forecast?latitude=37.3861&longitude=-122.0838&current_weather=true`
      * This will return weather data for the specific location, such as the current temperature, weather conditions, etc.
4. Display Weather Data:
      * The weather data returned from Open-Meteo is processed and displayed on the app, providing the user with real-time weather information for the location they entered.
* Example:

 ```js
  <!-- HTML Input for Zip Code -->
<input type="text" id="zipCode" placeholder="Enter zip code">
<button onclick="getWeatherFromZipCode()">Get Weather</button>
<div id="weather-info"></div>

<script>
// Function to convert zip code to latitude/longitude and fetch weather
function getWeatherFromZipCode() {
    const zipCode = document.getElementById("zipCode").value;
    
    // Request coordinates from Nominatim API
    fetch(`https://nominatim.openstreetmap.org/search?postalcode=${zipCode}&country=USA&format=json`)
        .then(response => response.json())
        .then(data => {
            if (data && data[0]) {
                const lat = data[0].lat;
                const lon = data[0].lon;
                
                // Request weather data from Open-Meteo API
                fetch(`https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current_weather=true`)
                    .then(response => response.json())
                    .then(weatherData => {
                        // Display weather info
                        const temperature = weatherData.current_weather.temperature;
                        const condition = weatherData.current_weather.weathercode;
                        document.getElementById("weather-info").innerHTML = `Temp: ${temperature}°C, Condition: ${condition}`;
                    })
                    .catch(error => {
                        console.error("Error fetching weather data:", error);
                    });
            } else {
                console.error("Zip code not found.");
            }
        })
        .catch(error => {
            console.error("Error fetching coordinates:", error);
        });
}
</script>
   ```
### 2/24 - 3/2
* Started working on my MVP
* I added some HTML and CSS
* Created the placeholders to guide the user and made a submit button for the user to submit their input labeled "Get Weather"
* Tried to make the button work, when clicked gives weather, however there was something was wrong in my code.
* This was my code:
  ```js
   function getWeather() {
            var zip = document.getElementById("zip").value;

            // Fetch the coordinates (latitude and longitude) for the zip code
            var geoResponse = await fetch(`https://nominatim.openstreetmap.org/search?postalcode=${zip}&format=json`);
            var geoData = await geoResponse.json();

            if (geoData[0]) {
                // Fetch the weather data using the coordinates
                var weatherResponse = await fetch(`https://api.open-meteo.com/v1/forecast?latitude=${geoData[0].lat}&longitude=${geoData[0].lon}&current_weather=true`);
                var weatherData = await weatherResponse.json();
                
                // Display the temperature in the result div
                document.getElementById("result").innerText = `Temperature: ${weatherData.current_weather.temperature}°C`;
            } else {
                document.getElementById("result").innerText = "Invalid zip code.";
            }
        }
  ```
* Learned how to use await fetch
* To fetch data from a public API like Open-Meteo (for weather) or Nominatim (for geolocation based on zip codes), you can use JavaScript's fetch() method along with async and await.
* `await fetch()` is part of JavaScript's async/await syntax, used to work with asynchronous code, especially when making network requests like fetching data from an API.
* fetch():
    * fetch() is a built-in JavaScript function used to make HTTP requests to fetch data from an external resource (like an API, server, or file).
await:
    * await is used inside an async function. It pauses the execution of the function until the promise is resolved, which makes the asynchronous code look and behave more like synchronous code.
    * When you use await, JavaScript waits for the promise to resolve and then moves on to the next line of code.
 * In my example, when the user enters a zip code and clicks "Get Weather", the getWeather() function is called. The function first fetches the coordinates (latitude and longitude) of the zip code by calling the Nominatim API with the zip code.
* Next Steps:
     * Find my error and display basic weather information
### 3/3 - 3/9
* I was able to get the temperature of you button clicked.
* This is my new code:
```js
     async function getWeather() {
    // Get the zip code entered by the user
    var zip = document.getElementById("zip").value.trim();
    var resultDiv = document.getElementById("result");
    resultDiv.innerText = "Fetching data..."; // Show fetching message

    try {
        // Fetch geolocation data based on the zip code
        var geoData = await (await fetch(`https://nominatim.openstreetmap.org/search?postalcode=${zip}&country=us&format=json`)).json();

        // If no data found for the zip code, show an error message
        if (!geoData.length) return (resultDiv.innerText = "Invalid zip code.");

        // Get latitude and longitude from geolocation data
        var lat = geoData[0].lat;
        var lon = geoData[0].lon;

        // Fetch weather data using the latitude and longitude
        var weatherData = await (await fetch(`https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current_weather=true`)).json();

        // Display weather data or show an error message if not available
        resultDiv.innerText = weatherData.current_weather 
            ? `Temperature: ${weatherData.current_weather.temperature}°C` 
            : "Weather data not available.";
    } catch {
        // If an error occurs, show an error message
        resultDiv.innerText = "Error fetching weather data.";
    }
}
```

* I learned that my second try work because it has the async keyword, which allows the use of await to pause the function until data is received. The second version doesn't work because it is missing the async keyword, and await can only be used inside async functions.
* In my first try, the zip code wasn't trimmed, meaning extra spaces could cause problems. I added .trim() to fix this.
*  The first try didn’t handle errors like failed requests. I added a try-catch block to catch errors and show a message instead of breaking the code.
*  `async` and `await`: I now understand that await only works inside an async function. Without async, the function can't use await to pause and wait for data.
*  I learned that using `.trim()` on input like the zip code is important to remove extra spaces that could cause errors in API requests.
*  Error Handling: You learned how to handle errors with a try-catch block, which prevents your code from breaking and allows you to show user-friendly error messages when something goes wrong like if the API request fails.
*  Next Steps:
     * Add what to wear based on the temperature.
  ### 3/17-3/23
  * Learned more about how to add clothing suggestions based on weather.
  * This is what I tried while learning.
  * I wanted to show images that represent different weather conditions (sunny, rainy, cloudy, etc.). To do this, I mapped weather conditions from the API response to corresponding image files.
```js
    const weatherImages = {
        Clear: "sunny.jpg",
        Rainy: "rainy.jpg",
        Cloudy: "cloudy.jpg",
        Snowy: "snowy.jpg"
    };
    
    function updateWeatherImage(weatherCondition) {
        const weatherImage = document.getElementById("weather-image");
        weatherImage.src = weatherImages[weatherCondition] || "default.jpg"; 
    }
```
* When the API returns a weather condition, the function updates the src attribute of the <img> tag in the HTML.
* If the weather condition is not found in the weatherImages object, a default image is shown.
* To make the app more engaging, I also added images for clothing suggestions based on the temperature.
```js
function suggestClothing(temp) {
    let suggestion = "";
    let imageSrc = "";

    if (temp >= 25) {
        suggestion = "Wear light clothes like a t-shirt and shorts.";
        imageSrc = "summer-outfit.jpg";
    } else if (temp >= 15) {
        suggestion = "Wear a light jacket or hoodie.";
        imageSrc = "fall-outfit.jpg";
    } else {
        suggestion = "Wear a heavy coat, scarf, and gloves.";
        imageSrc = "winter-outfit.jpg";
    }

    document.getElementById("clothing-suggestion").innerText = suggestion;
    document.getElementById("clothing-image").src = imageSrc;
}
```
* Depending on the temperature, the function selects an appropriate outfit description and an image.
* The innerText of an HTML element is updated with the suggestion.
 *  Next Steps:
     * Add what to practiced to my MVP
  
### 3/24 - 3/31
* I learned how to allow users to switch between Celsius and Fahrenheit
1.   Add a Dropdown Menu

  ```html
   <select id="unit">
       <option value="C">Celsius</option>
       <option value="F">Fahrenheit</option>
    </select>
  ```

* The id="unit" allows JavaScript to reference this dropdown.
* The value="C" and value="F" help determine the selected unit. 

2. Modify the JavaScript Function
* The getWeather() function should now:
    * Read the selected unit from the dropdown.
    * Convert the temperature if Fahrenheit is chosen.
    * Display the correct value based on the user's selection.
Steps Inside getWeather()
  * Get user input (zip code and selected unit).
 
```js
    var zip = document.getElementById("zip").value.trim();
    var unit = document.getElementById("unit").value;
```
 
