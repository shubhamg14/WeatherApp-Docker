# WeatherApp-UI
UI to fetch and display data using WeatherApp-API (API functionality can be found @https://github.com/shubhamg14/WeatherApp-API

This implementation of an UI follows a dynamic approach that uses asynchronous JavaScript requests to send the user-inputted data to the REST API(WeatherApp-API - @https://github.com/shubhamg14/WeatherApp-API) , receive the structured results, and then publish them into the page without refreshing the whole page again.

This Webpage takes an input date and then plot the Forecasts TMIN, TMAX for next five days.

## UI overview

        1. This UI has been implemented using Javascript for Asynchronus call, so that whenever value gets updated, page does not                  refresh.
        2. For HTML part Bootstrap 4 CSS has been used to implement layout and Navbars.
        3. CanvasJS has been used to populate graphs for weather forecasts.

## The UI has the following functionality:

**_Historical_** - Enter a date from 1st January'2013 - 28th March'2019 and you will get the minimum and maximum temperature for that day.

Date is required in a YYYYMMDD format and then when you click submit button,you will get Maximum and Minimum temperature for that day

   ![alt text](https://github.com/shubhamg14/WeatherApp-UI/blob/master/images/historical_empty.PNG)

   ![alt text](https://github.com/shubhamg14/WeatherApp-UI/blob/master/images/historical_populated.PNG)

**_Forecast_** - Enter any existing and future date and you will get a weather forecast in a table format as well as a line graph.
The Forecast may not be accurate as it is calculated by taking the running average of temeperature for past 365 days.

Date is required in a YYYYMMDD format and then when you click submit button,you will get Forecast for next 7 days

  ![alt text](https://github.com/shubhamg14/WeatherApp-UI/blob/master/images/forecast_empty.PNG)
  
  ![alt text](https://github.com/shubhamg14/WeatherApp-UI/blob/master/images/forecast_populated.PNG)

**_OpenWeather_** - This page displays the weather forecast for next 5 days which is fetched from a third party API (Openweathemap.com).
This page outputs the forecast in a table format as well as graph.

This page outputs forecast for next 5 days 

  ![alt text](https://github.com/shubhamg14/WeatherApp-UI/blob/master/images/openweather_populated.PNG)

## Following packages are required to run this code base:

    1. Bootstrap 4 (https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css)
    2. Jquery 3 (https://code.jquery.com/jquery-3.3.1.slim.min.js)
    3. Ajax (https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js)
    4. Javascript (https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js)
    5. CanvasJS - For plotting graphs (https://canvasjs.com/assets/script/canvasjs.min.js)
    
 ## Running Code
 
        1. First create a project directory in your local machine and then pull the flaskapp.py and templates folder from this repository into your project folder.
        2. Install following packages (Steps can be found at @https://github.com/shubhamg14/WeatherApp-API
            Python (sudo apt install python)
            pip 19.0.3 (sudo apt install python-pip)
            Flask 1.0.2 (sudo pip install flask)
            requests 2.21.0 (sudo pip install requests)
        3. Run python3 flaskapp.py in your command prompt and the application will go live on your localmachine at "http://127.0.0.1:5000/"          

