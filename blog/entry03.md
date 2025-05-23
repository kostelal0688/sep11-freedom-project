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
and [Geolocation Article ](https://www.w3.org/TR/geolocation/).

*  Here’s how you can use the Geolocation API in the browser to get the user's current location and then use that information to fetch weather data:
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

### Next Steps
Next, I want to improve error handling and user feedback in my app. This includes handling cases when the Open-Meteo API fails or when users deny location access. I’ll make sure the app shows helpful error messages so users know what went wrong.

I also plan to explore more features of the Open-Meteo API, like adding hourly forecasts and extra weather data such as wind speed, humidity, and precipitation. Additionally, I want to add a 7-day forecast so users can see the upcoming weather. This will make the app more useful and informative.

## Engineering Design Process 
I’m currently in steps 2 and 3 of the engineering design process, where I’m diving into Open Meteo and experimenting with my code to better understand its features. I’ve been testing the addition of weather icons based on the data I get, which helps the app’s visual appeal. Another key update is the zip code feature I’ve implemented, where users can enter a zip code to retrieve weather information for that location, using the Nominatim API to convert the zip code into coordinates. Once I’ve gathered enough data, I’ll move on to step 4. In this phase, I’ll start planning the best solution for my app by selecting the most useful features, and determining the best way to display the weather information clearly for the user.
## Skills   
Some skills that I’ve learned from working on this blog are **Problem decomposition** , and **How to learn**

### Problem decomposition
I used problem decomposition to break my weather app project into smaller, manageable tasks. Instead of doing everything at once, I focused on one feature at a time. First, I learned how to get weather data from the Open Meteo API. Then, I worked on displaying information like temperature and wind speed. After that, I added weather icons and a feature that allows users to enter a zip code for specific location data. By breaking the project into smaller steps, I could focus on solving one problem at a time and gradually build the app. This helped me stay organized and make steady progress.

### How to learn
I learned on my own by looking up tutorials, reading documentation, and experimenting with code. Whenever I didn’t know how to do something, I searched online for solutions or examples. For instance, when I started using the Open Meteo API, I read the official guide and checked out other people's examples to understand how it worked. I also tried things out by myself, changing parts of the code to see what would happen. If something didn’t work, I researched and tried again. This hands-on approach helped me learn quickly.

## Summary
Overall, I’m excited about the progress I’ve made and look forward to continue to work on the project.
