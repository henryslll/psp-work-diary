# Tips for this week


https://github.com/Pelwis01/team-recipe-book

recipe attempt above ^^^

we decided to research key rewuirements, user stories, cattle parasites, how to host, find data for project.

my personal research

My initial understanding broken down

The app needs farmers to look at an area on a heatmap of the uk
Then the farmer picks a date historically or within the next 2 weeks
App then gathers weather data 
App then applies parasite risk rule
Updates map 

Front end (map/date picker)
Backend API
Weather API
Apply parasite rules
Update area with risk score
Show on heatmap

FOR WEATHER DATA
Open meteo
Gives historic plus two week forecasts given in gridded areas
Temp, rainfall, humidity

How we can use
Pull data from selected dates
Find out mean temperature on that day and rainfall over last week or two


Specific Parasite logic
Score (1-3) -> non met = 0, one met= 1, both met= 2

Gastrointestinal nematodes
(1)If mean temp >= 10 degrees AND  (2) rainfall > 50mm over past 14 days = high GN risk

Liver fluke
(1)if rainfall >=100mm over the past 30 days AND soilwetness >= 0.7 = high LF risk

Ticks
(1)if temp >= 7 degrees AND (2)upland region = possible tick risk

General Combined risk score
WeatherRisk = f(temp, rainfall)
ExposureRisk = cattle_density
LandRisk = soil_wetness

Final Risk =(0.5 × WeatherRisk)+ (0.3 × ExposureRisk)+ (0.2 × LandRisk)

Then normalise between 0-100 and draw heatmap

MAP idea
Traffic light system/ heatmap

When area clicked 
Popup = “based on last 14 days: avgtemp=..., rainfall=..., cattledensity=..., parasiterisks=....”

Data storage
Static
Cattledensity
Soilwetness
Tickregion

Dynamic
Avgtemp
Totalrainfall
parasiterisk
