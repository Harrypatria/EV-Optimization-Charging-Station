## Electric Vehicle Optimization 

### Introduction/Business Problem: 
Electric Vehicles (EVs) are gaining popularity due to absence of local emissions, and certain technical advantages that EVs have over conventional vehicles (faster acceleration, no need for periodic service requirements etc.). This is not to say that there are no barriers to the widespread acceptance of EVs. One of the primary drawbacks is the lack of access to charging equipment at public locations.

In this project, we look at the city of Raleigh in North Carolina, where I currently reside. The objective is to try to come up with a siting analysis for public EV charging station installations - preferably close to local shops and restaurants so that people can charge their cars while getting groceries or sharing a meal with their loved ones. One of the indirect benefits of EV charging that is often talked about is contribution to the local economy - i.e. people tend to spend money on nearby shops when waiting on charging their EVs.

To be specific, the area of interest in this case is within a 100 km radius of downtown Raleigh in North Carolina. This approximately covers the towns of Durham, Raleigh and Chapel Hill. As of 2020, the population of the larger Raleigh-Durham-Chapel Hill Combined Statistical Area (CSA) is estimated at 2.03 million. Hailed as a technological hub within the state, the mean age of residents range between 26 to 35 years. This area may be considered a suitable case study location for testing out algorithms ranking retail facilities that could benefit from EV charger installations.

Note that the approach that I am taking is pretty simplistic - I am aiming to identify retail locations (primarily grocery shops, restaurants and some service industries) that have relatively few EV chargers in the vicinity. A list of suitable retail locations that could benefit from an EV charging installation in its neighborhood is provided as input to a clustering algorithm. This algorithm determines locations that could improve access to EV charging in our region of interest.
Outputs include a map with clusters of retail locations that could benefit from EV charger installations and a list of suitable locations for EV charging installations.

- 1.	Leverage AFDC to download NC’s EVSE locations: Select public L2/DCFC EVSEs only in the RDU-Chapel Hill area zip codes. Only select Name, Address, Charging Level and Coordinates (Lat, Long)
- 2.	Use foursquare API to download places of interest within RDU-Chapel Hill Area: Identify trending venues and ratings. How many of these are restaurants
- 3.	Use Python’s geocoding package: https://pypi.org/project/geocoder/ to track down lat/long of all restaurants/trending restaurants
- 4.	Generate a data frame
- 5.	Filter out restaurants within 5 miles of either an L2 or DCFC + think of other criteria for filtering
- 6.	Map this using Folium – think of heat maps/other ways to visualize the data
- 7.	Use k-means clustering to cluster those locations to create centers of zones containing good locations. Those zones, their centers and addresses will be the final result of our analysis.

### Discussion
While this project does a good job demonstrating how data science can be used to inform energy 
infrastructure siting decisions, the analysis could be improved in many different ways. A few are 
listed here but should not be considered an exhaustive list:
- (a) Socio-economic as well as demographic factors need to be considered when prioritizing 
siting locations. Here is an excellent article summarizing policies and actions being taken to 
expand access to electric transporation among low income groups and apartment dwellers
- (b) Siting analysis may need to take into considerations the practicality of EV charging 
installations - zoning permits, transmission capacity to support supply of electricity for EV 
charging etc. are some factors that could affect EV charging installations
- (c) Demand for EV charging is another really important factor. If there are not enough EVs 
driving through the region that need to stop and charge - there may not be any incentive for 
installation of EV chargers. North Carolina DMV has recently started releasing EV registration 
data in NC counties . This could indicate how many EV owners currently reside in NC. Market 
research could also be performed to explore the out-of-state EV traffic passing through NC.

### Conclusion
This project provides a simple example of utilization of k-means clustering technique in the 
clean energy sector. Data cleaning and manipulation, application of algorithms, and subsequent 
data visualization are the primary steps involved in any problem that needs to be solved using 
data analytics. I hope that this notebook provides a source of reference for those starting to 
explore data-driven solutions to their business problems.

