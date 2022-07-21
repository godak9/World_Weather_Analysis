# World Weather Analysis using the OpenWeatherMap API and the Google Directions API
## Project Overview 
Travelers like to be informed about the weather conditions at their vacation destination before they travel. Sometimes travelers even change their travel destination depending on the weather conditions and their preferences. The purpose of this project gather weather data in random cities across the world and provide travellers with a tool to determine their ideal travel destination(s).

Jupyter Notebook was used to write code to retrieve weather data, to retrieve customer weather preferences using input statements, to generate a marker layer map of these locations based on the input statements, to create a travel itinerary that shows the route between four cities based on the customer's preferences, and finally, to create a marker layer map with a pop-up marker for each city in the itinerary. 

The project was broken down into three sections.

## Section 1: Obtaining Weather Data
A set of random latitudes and longitudes using the NumPy module. The nearest city for each coordinate was received using the CitiPy module. An API call was performed with OpenWeatheMap using the Requests module to retrieve latitude and longitude, maximum temperature, percent humidity, wind speed, and a weather description for each located city.

This code can be found in the Weather_Database folder in the Weather_Database.ipynb file. Weather data for 682 cities was found and saved to a DataFrame. This DataFrame was saved and exported as CSV file named WeatherPy_Database.csv found in the Weather_Database folder. 

## Section 2: Creating a marker layer map based on customer preferences
The WeatherPy_Database.csv containing the weather information for the 682 cities was read into a DataFrame in a seperate file so a filtered search could be performed on data based on customer preferences. Two input boxes were generated for the customer to input their minimum and maximum temperature preferences. In the code, I used a minimum of 70 degrees fahrenheit and a maximum of 90 degrees fahrenheit. 

A new DataFrame was then generated around these preferences. Then, this DataFrame was changed so that a "Hotel Name" column was added. This column's data was populated by making an API call with the Google Maps API and JSON data was retrieved. Hotels within a 5000 meter radius of each city were found. 

A marker layer map was created using the Gmaps module where each city that had a hotel within a 5000 meter radius was marked. Code was added to create an info box that was displayed when the markers were clicked. The info box contained the city name, the country code, the weather description, and the maximum temperature for each city.

This code can be found in the Vacation_Search folder in the Vacation_Search.ipynb file.  
The DataFrame containing the "Hotel Name" column was saved and exported as CSV file named WeatherPy_vaction.csv found in the Vacation_Search folder.
A snippet from the marker layer map can be seen below: 

![WeatherPy_vacation_map](https://user-images.githubusercontent.com/104794100/180322801-801db45b-d71f-4640-9dd4-fbf599a5e68b.png)

## Section 3: Creating a travel itinerary map containing four cities within the customer's prefernces
 The WeatherPy_vaction.csv containing the weather and hotel information for the cities that fell into the customer's preference (Min temp: 70, Max temp: 90) was read into a DataFrame in a seperate file. Four cities were choosen from this DataFrame to create a vacation itinerary route to travel between the four cities. The starting and ending location was Asyut, Egypt. The three cities choosen to stop at were (in order) Cairo, Egypt, Marsa Matruh, Egypt, and Darnah, Libya. The travel mode between these cities was listed as either driving, bicycling, or walking. 

The information from the DataFrame for these four cities was extracted and then combined into a new DataFrame. A marker layer map was created containing a marker for each of the four cities. Code was added to create an info box that was displayed when the markers were clicked. The info box contained the city name, the country code, the weather description, and the maximum temperature for each city.

This code can be found in the Vacation_Itinerary folder in the Vacation_Itinerary.ipynb file. Weather data for 682 cities was found and saved to a DataFrame. 
The vacation itinerary route for the four cities can been seen below:  

![WeatherPy_travel_map](https://user-images.githubusercontent.com/104794100/180324365-333439b9-f77d-46ea-95a2-8be01b3816ad.png)

A marker layer map for the four cities can been seen below: 

![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/104794100/180324511-7c8300cc-3ac9-48b6-9ab3-001fed6a8789.png)



