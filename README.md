# PlanMyTrip Beta

## Overview
Conducted a world weather analysis using the Open Weather Map API to pull weather data from around the world and the Google Maps API to plan a trip. Users of PlanMyTrip can input their preferred temperature range and find cities to travel to based on their preferences. Once the user has determined where they would like to travel, they can use PlanMyTrip to create a travel itinerary to find the route between cities, as well as hotels and current weather information for each city.

## Analysis

### Generating a Vacation Map
After generating a set of 2,000 random latitudes and longitudes, the citipy module was used to pull a list of cities close to each latitude and longitude combination. The Open Weather Map API was used to retrieve weather data for all the cities and a list was created to store the weather data which included the latitude and longitude, current weather description, maximum temperature, humidity, cloudiness, wind speed, as well as the city and country. The data was cleaned to remove any cities with missing weather data. Following the weather analysis, a "Customer Travel Destinations Map" was set up using the Google Maps API to find hotel information for relative cities and mark the travel destinations on a map. After importing the stored weather data, a prompt is set up for the user to input their minimum and maximum temperature preference criteria. The city data is then filtered to only show cities with the preferred temperature criteria and any rows with missing information are removed. In addition to the weather information for these cities, a hotel dataframe is set up to search for hotels within 5000 meters and cities without hotel information are dropped. Finally, a dynamic map with city markers that include both the relevant weather and hotel information is set up so users can identify which cities to travel to. An image of this map is below.

*WeatherPy Vacation Map:*
![WeatherPy_vacation_map.PNG](https://github.com/borkard/World_Weather_Analysis/blob/main/Vacation_Search/WeatherPy_vacation_map.png)

### Developing a Travel Itinerary
Using the vacation map, a user can identify cities to travel to and create a travel itinerary for anywhere in the world. An example for creating an itinerary between four Argentinian cities (Moron, Comodoro Rivadavia, Punta Arenas, and Ushuaia). Separate dataframes were created for the city in which the trip would begin and end (Moron) and for each stop along the way (Comodoro Rivadavia, Punta Arenas, and Ushuaia) and the latitude and longitude pairs for each dataframe were pulled. Using these latitude and longitude pairs, waypoints were set for each stop and a direction layer map was set up for a driving route between them. The map for the travel route is below.
![WeatherPy_travel_map.PNG](https://github.com/borkard/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map.PNG)

Markers with hotel and weather information for the relevant cities were then added to the map (displayed below).
![WeatherPy_travel_map_markers.PNG](https://github.com/borkard/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map_markers.PNG)
