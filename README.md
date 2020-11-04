# Python API - Weather Analysis

## Background
In this project, I was asked to use Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

## Observations
After carefully running the analyiss following observations were made:
1. Max temperature is the variable that shows a prominent observable trend. As the latitude go toward far ends the max temperature tends to start dropping. For most locations near the equatar, in range -20 to 40, the temperature reach max values.
2. Humidity, Cloudiness and Windspeed are quiet variable from location to location and do not show an observable trend with latitude coordinates.
3. The goodness of fit (R-squared) for humidity, cloudiness and windspeed is also very low explaining high variance in data.
4. For humidity it can be observed that southern hemisphere usually has more number of cities with high humidity. This can be a data bias as there more number of cities in northern hemisphere dataframe as compared to southern hemipshere

## Part I - WeatherPy

In this example, I created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, you'll be utilizing a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

I built a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot added a sentence too explain what the code is and analyzing.

I ran linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

### Part II - VacationPy

I used my skills to plan future vacations. Used jupyter-gmaps and the Google Places API for this part of the assignment.

* Created a heat map that displays the humidity for every city from the part I.

  ![heatmap](VacationPy/Images/heat_map2.png)

* Narrowed down the DataFrame to find the ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Dropped any rows that don't contain all three conditions.

* Used Google Places API to find the first hotel for each city located within 5000 meters of the coordinates.

* Plotted the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](VacationPy/Images/final_map2.png)
