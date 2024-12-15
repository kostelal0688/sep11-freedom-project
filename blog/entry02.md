# Entry 2 (Learning My Tool)
##### 12/9/24
During the past few weeks I have been learning more about JSON APIs Open Meteo. To learn more about the tool I created a website where a user can check the weather in several cities and get clothing suggestions based on the temperature, with the ability to toggle between Celsius and Fahrenheit for temperature units. I used [Open Meteo](https://open-meteo.com/) which is the official documentation for the Open Meteo API, with detailed information on how to make requests for weather data, including temperature, wind, precipitation, etc. Let’s break it down into its components:

HTML Structure:
 * The HTML structure includes a heading, radio buttons to toggle between Celsius and Fahrenheit, a container (div with id="weather-info") where the weather data and clothing suggestions for different cities will be displayed, and a <script> tag where JavaScript functionality resides.
html
  ```html
     <h1>Dress Based on Weather</h1>
     <label><input type="radio" name="unit" id="celsius" checked> Celsius</label>
     <label><input type="radio" name="unit" id="fahrenheit"> Fahrenheit</label>
     <div id="weather-info"></div>
  ```





[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
