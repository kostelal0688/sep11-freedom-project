# Entry 4 (Start the MVP)
##### 3/10/25
## Content
 In the past few weeks, I’ve been learning how to use the Open-Meteo API to get weather data for my app. I’ve also been learning how to handle requests in JavaScript using async and await, which helps get the data from the API without freezing the page. To help with this, I used resources like the [https://open-meteo.com/en/doc](Open-Meteo API Documentation)

### Progress Made:

At first, I added some HTML and CSS to make the page look nice and easy to use. I created a "Get Weather" button and tried to make it fetch the weather when clicked. My idea was that when the user inputs their zip code and clicks the button, they would see the weather for their location. However, my first attempt didn’t work as expected because my code wasn’t handling the API requests properly. The button didn’t trigger the fetch correctly, and the weather data wasn’t displaying on the page.

I realized the issue was that I wasn’t using async and await properly to handle the API calls, which caused some delays and errors. I also needed to trim the zip code input to remove unnecessary spaces, and I didn’t have error handling for when the fetch failed. Once I fixed these issues, the button started working and successfully fetched the weather data for the zip code entered.

* Here’s the first version of my code:

```js
 function getWeather() {
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

I found that I needed to use async and await properly. I also realized that I wasn’t trimming the zip code, so spaces might mess things up. After fixing these issues, I also added a try-catch block to handle errors, like when the API can’t fetch data. This is the code that works:

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



## Engineering Design Process 

## Skills   
Some skills that I’ve learned from working on this blog are ** ** , and ** **

### 

### 

## Summary


[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
