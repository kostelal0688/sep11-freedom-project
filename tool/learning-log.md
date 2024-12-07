

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
Tinkered by making a a simple weather-based dressing app using HTML, CSS, JavaScript arrays, functions, conditions, and loops. 
   *   tool/tinkering
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


<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
