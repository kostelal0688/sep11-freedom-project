# Entry 3 (Learning Tool)
##### 2/8/25

### Content
  Over the winter break, I have made significant progress in improving and expanding the weather app I started. I added weather icons to represent different conditions like sunny, cloudy, and rainy. Using the Open Meteo API, I was able to display these icons alongside the weather details, making the app more visually appealing. I also integrated the Geolocation API, so the app automatically detects the user’s location and shows the weather for that area, saving the user from manually entering their location.
  
##### Weather Icons Integration:
* Integrated weather icons based on conditions fetched from the API. For instance, if the weather is "Clear", it shows a sun icon, "Rainy" shows a rain cloud, and so on.
  
Example:
```js
if (weatherCondition === "Clear") {
    document.body.style.backgroundImage = "url('sunny.jpg')";
    weatherIcon.src = "sun-icon.png";
} else if (weatherCondition === "Rain") {
    document.body.style.backgroundImage = "url('rainy.jpg')";
    weatherIcon.src = "rain-icon.png";
}
```
Additionally, I implemented a feature that allows users to input a zip code to retrieve weather data for a specific location. This was made possible by integrating the Nominatim API, which converts the zip code into latitude and longitude coordinates. Once the coordinates are obtained, I use them to make a request to the Open Meteo API to fetch the weather data for that location. This allows users to quickly check the weather for any city or area by simply entering a zip code, making the app more convenient and accessible. It improves user experience by giving them more flexibility in accessing weather information without needing to know the exact geographic coordinates of their location. To learn how to enter a zip code to get weather data for that location I used these articles
[Using the Geolocation API](https://developer.mozilla.org/enUS/docs/Web/API/Geolocation_API/Using_the_Geolocation_API),
[Geolocation Article ](https://www.w3.org/TR/geolocation/)

## Engineering Design Process 

## Skills   


## Summary

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
