

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
 
### 11/18/24: 
* [Add icons to represent each weather](https://github.com/open-meteo/open-meteo/issues/789)
    * I could use this to add icons based on weather




<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
