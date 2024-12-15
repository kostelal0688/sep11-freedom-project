# Entry 2 (Learning My Tool)
##### 12/9/24
During the past few weeks I have been learning more about JSON APIs Open Meteo. To learn more about the tool I created a website where a user can check the weather in several cities and get clothing suggestions based on the temperature, with the ability to toggle between Celsius and Fahrenheit for temperature units. I used [Open Meteo](https://open-meteo.com/) which is the official documentation for the Open Meteo API, with detailed information on how to make requests for weather data, including temperature, wind, precipitation, etc. Let’s break it down into its components:

HTML:
 * The HTML includes a heading, radio buttons to toggle between Celsius and Fahrenheit, a container (div with id="weather-info") where the weather data and clothing suggestions for different cities will be displayed.
html
  ```html
     <h1>Dress Based on Weather</h1>
     <label><input type="radio" name="unit" id="celsius" checked> Celsius</label>
     <label><input type="radio" name="unit" id="fahrenheit"> Fahrenheit</label>
     <div id="weather-info"></div>
  ```
* I also used some simple CSS  to make the page look neat and presentable. 

```css
.city-info {
    background-color: #fff;
    border-radius: 8px;
    padding: 15px;
    margin: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    display: inline-block;
    width: 250px;
    text-align: left;
}
```
* JavaScript:
   * temperatureUnit stores the current unit for temperature (Celsius by default).
   * The cities array contains the details of the cities you want to fetch weather data for. It includes the name, latitude, and longitude of the cities.
```js
let temperatureUnit = 'C';  // Default to Celsius
const cities = [
    { name: 'Berlin', lat: 52.52, lon: 13.4050 },
    { name: 'London', lat: 51.5074, lon: -0.1278 },
    { name: 'New York', lat: 40.7128, lon: -74.0060 },
    { name: 'Tirana', lat: 41.3275, lon: 19.8189 }
];
```






[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
