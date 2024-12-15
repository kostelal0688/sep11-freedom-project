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
I also used some simple CSS  to make the page look neat and presentable. 

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






[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
