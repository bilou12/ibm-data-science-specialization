# Introduction / Business problem

In this project, I am going to rank cities based on their attractiveness.

The attractiveness will be measured by the number of recommended places and their type.

Some kind of recommend places such as "fast-food" will downgrade the attractiveness while others 
such as "regular restaurant" will bring a good point.


# Data

To solve this problem, I am going to use the geolocator api and the foursquare api.

From the geolocator api, I am going to fetch the latitude and longitude of the several cities I am willing to compare.

I will use these as input to the Foursquare API venues/explore to retrieve the venues of each city and compare them.