Java plan:

- First Steps -
  i need somehow to make the application show the forecast for certain days...
  but the code in html is too big and it is not wise to create so many different id's
  cause it will overcomplex the code. Instead i am injecting the html into java.

Now in java first things first, i make a function about the forecast
which is gonna make my life easier. i cannot really mutliply my divs
5 times, because it's going to replace every time the forecast.innerHTML.
Instead i am gonna use loops. So basically what i wanna say is ´i wanna add this code 5 times´
but every time it should show a different day and temp. The loop is going to allow us loop through an array
and this array of days or of data gonna have 5 items and then we are gonna display this 5 times. I am gonna start by creating an array of days and insert my forecast.innerHTML inside the loop. This basically gonna take these 5 days and loop through in each one of them at a time. But in order to make it work properly, i have to oncatenate a massive a string. So i create a new variable and i make it so it can call multiple times my function.

- But why is this working? -
  Steps:

1. call a function called ´displayForecast´ which is going read the 10 line function
2. create an array with 5 days
3. create a variable with nothing in it, but then we wanna put inside this variable
   next step is to enter a valid API for it

-API function-

Create a new function which is gonna make an Api call and then display the forecast. (getForecast). It works kinda like the searchcity function but we use it for a forecast.
To get the information inside our code, we use Axios and we send it to our latest function ´displayForecast´. It will create another key variable for forecast.
Then the displayForecast it should expect a response.
Also we need to relocate getForcast call inside the refreshWeather function,that way we know the city will be displayed corretly. So we asked to get the forcast with the actual name of city from the api

-Actual Forecast data-

1. analyze with console.log our data
2. first we display the temperatures. Instead of looping the days we had inside our displayForecast, we can simply remove them and we have to loop through by
   replacing days with response.data.daily
3. next we are replacing our texts inside the div with actual data
4. we are adding icons as well. Moved the class inside the img instead of the div, so we can target it easier in css directly from javascript
5. we set an index with an if, in order to make it display 5 days instead of 7
6. Last step is to add the days and for that we need to make another function for the days, named: formatDay(timestamp)
7. After creating the function we replace inside the div with formatDay(day.time)
