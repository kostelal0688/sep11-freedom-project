# Plan

## Tool: JSON APIS
## Product: Dress based on Weather App

---

## Timeline

### MVP
 - [ ]  **Create a simple webpage for user zip code (2/17 - 2/21)**
  - [ ] Designing a form to accept user zip code meaning create something interactive where users can enter their zip code
      - [ ] Add placeholders to guide the user, like “Enter your zip code”.
       - [ ] Make a submit button for the user to submit their input labeled "Get Weather"
- [ ] **Display basic weather information (2/22 - 3/1)**
  - [ ] Display temperature and weather condition (clear, rainy, etc.)
       - [ ] Format the weather data in a readable and user-friendly way
- [ ]  **Implement radio buttons or a dropdown for temperature units Celsius/Fahrenheit (3/3 - 3/7)**
  - [ ]  Add two radio buttons for the user to select temperature units
      - [ ]  When a radio button is clicked, it should toggle the temperature unit of the displayed data.
- [ ]  **Add basic weather-based clothing suggestions (3/9 - 3/21)**
  - [ ]  Define clothing suggestions based on temperature (ex: "Hot: Wear shorts" or "Cold: Wear a jacket")
       - [ ]  Add image of clothing
       - [ ]  Use conditional statements to display the correct suggestion
### Beyond MVP

- [ ] **Add weather icons based on weather condition**
  - [ ] Use weather condition data from the Open-Meteo API to display corresponding weather icons (ex: sun for clear, cloud for cloudy, etc.)
       - [ ] Ensure icons update dynamically based on the condition
- [ ] **Implement geolocation feature**
  - [ ] Use the Geolocation API to fetch the user’s current location
       - [ ] Automatically display weather for the user’s location without inputting a zip code
- [ ] **Implement 7-day weather forecast**
  - [ ] Extend the Open-Meteo API request to include forecast data for the next 7 days
       - [ ] Display the forecast for each day in the future


<!-- EXAMPLE

## Tool: APIs
## Product: Green Glass Door riddle app

## Timeline

### MVP

- [ ] Front-end
  - [x] Webpage to collect input from user (deadline: 4/15)
  - [ ] Webpage to display "yes, but a ___ can't" or "no, but a ___ can" (deadline: 5/1)
- [x] Back-end
  - [x] Use regex to test whether or not the word can go through the GGD (deadline: 3/1)
  - [x] Use the Twinword API to find related words (deadline: 3/15)
    - [ ] Iterate through the words until an opposite example can be found (deadline: 4/1)

#### Beyond MVP

- [ ] Use another API to make sure the opposite example is a noun
- [ ] Automate notification of API limit to make sure I don’t exceed free quota
- [ ] A multiple choice quizzer that will test the user’s knowledge of the solution

-->





<!-- DO NOT USE THIS YET

| Name | Glows | Grows |
| -------- | ------- | ------- |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |
|   |   |

-->
