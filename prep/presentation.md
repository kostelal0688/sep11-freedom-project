# Presentation Plan

## Hook
* Ever find yourself staring at your closet, totally unsure of what to wear because you have no clue what the weather’s actually like outside?

## Product
* My weather-based clothing suggestion website can help you! Simply enter your zip code, and the site will provide the current weather along with outfit suggestions for that weather. It's your personal wardrobe assistant that ensures you’re always dressed for the weather!

## Process
* Wireframe Example:
    * Show the wireframe of my project because it helped me start.
* Plan
  * MVP: What I did: I integrated the Nominatim API to convert zip codes into coordinates (latitude and longitude). If the zip code is valid, the app then uses those coordinates to fetch weather data from the Open-Meteo API.
  * Beyond MVP: Added Fahrenheit for temperature units, making the app more accessible to users from different regions.
 * Code snippets
     * Beyond MVP
     * Both APIS 
     * Show examples of how the API calls were set up and how you handled error responses for invalid zip codes.
     * Challenge: Demonstrate how you processed the API responses and got the weather data to display it effectively
 

## Conclusion
* [https://kostelal0688.github.io/sep11-freedom-project/]
* Takeaways
   * When you’re stuck, just start drawing: If you don’t know where to begin, stop panicking and grab a paper. Sketching out your ideas can help you figure out where to start.
   * Keep it simple: The basic feature—weather-based outfit suggestions—was easy to build but really helpful. It taught me to focus on one simple idea first.
   * Error handling matters: I learned how important it is to give users clear feedback when something goes wrong, like with invalid zip codes.
   * Improvement is important: The MVP worked, but adding new features like temperature unit options made it better. I learned that small updates can make a big difference.
   * Real experience: This project gave me hands-on experience with APIs and working with real data, which was a great learning opportunity.



<!-- EXAMPLE

## Hook
* Verbal riddle of GGD

## Product
* GIF/Demo of example/non-example

## Process
* Flowchart of plan
  * MVP: noun -> door -> yes/no
  * Beyond MVP: noun -> word relation API -> noun API -> yes/no, with counterexample
* Code snippets of:
  * MVP
  * Both APIs
  * Challenge with API keys

## Conclusion
* [URL to project]
* Takeaways
  * Less = more: the heart of the riddle was one line of code; it obviously took more to make the entire thing work, but one complicated line of regular expressions was essentially the solution to the riddle
  * Expect the unexpected: it’s important to budget time for things you don’t account for; for example, I didn’t consider the fact that I would need another entire API to detect nouns
  * Determination is key: ironically enough, I had to make my API keys private. At first, it didn’t seem like it was possible, which meant I couldn’t publish my app. But after all of that hard work, I was determined to find a solution, and I found it in config variables.
* "Presentation can’t, but a speech can"


-->
