# Entry 4 (Start the MVP)
##### 3/10/25
## Content
 In the past few weeks, I’ve been learning how to use the Open-Meteo API to get weather data for my app. I’ve also been learning how to handle requests in JavaScript using async and await, which helps get the data from the API without freezing the page.

### Progress Made:

At first, I added some HTML and CSS to make the page look nice. I created a "Get Weather" button and tried to make it fetch the weather when clicked. But my first attempt didn’t work as expected because my code wasn’t handling the API requests properly.
 * Here’s the first version of my code:
```js
 async function getWeather() {
    var zip = document.getElementById("zip").value;
    var geoResponse = await fetch(`https://nominatim.openstreetmap.org/search?postalcode=${zip}&format=json`);
    var geoData = await geoResponse.json();
    if (geoData[0]) {
        var weatherResponse = await fetch(`https://api.open-meteo.com/v1/forecast?latitude=${geoData[0].lat}&longitude=${geoData[0].lon}&current_weather=true`);
        var weatherData = await weatherResponse.json();
        document.getElementById("result").innerText = `Temperature: ${weatherData.current_weather.temperature}°C`;
    } else {
        document.getElementById("result").innerText = "Invalid zip code.";
    }
}
```
### What I Learned:

I found that I needed to use async and await properly. I also realized that I wasn’t trimming the zip code, so spaces might mess things up. After fixing these issues, I also added a try-catch block to handle errors, like when the API can’t fetch data.

    * Here’s the updated code that works:



## Engineering Design Process 

## Skills   
Some skills that I’ve learned from working on this blog are ** ** , and ** **

### 

### 

## Summary


[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
