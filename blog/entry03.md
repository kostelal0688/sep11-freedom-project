# Entry 3 (Learning Tool)
##### 2/8/25

### Content
  Over the winter break, I have made significant progress in improving and expanding the weather app I started. I added weather icons to represent different conditions like sunny, cloudy, and rainy. Using the Open Meteo API, I was able to display these icons alongside the weather details, making the app more visually appealing. I also integrated the Geolocation API, so the app automatically detects the user’s location and shows the weather for that area, saving the user from manually entering their location.
  
Weather Icons Integration:
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

## Engineering Design Process 

## Skills   


## Summary

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
