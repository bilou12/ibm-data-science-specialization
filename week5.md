# Introduction / Business problem

As I have lived in many countries, I have been exposed to many cultures.

So I wanted to use this project to explore what are the most common venues by cities and 
see if this is in line with the cross-cultural differences that we could expect.

This analysis could be leveraged by a business person or any international company before setting-up in 
a foreign country to assess whether the local market will match it product and business.

Let's not forget that when it comes to set-up a business, it's important for the investor to be at the right time 
and most importantly at the right place.


# Data

The data needed for this analysis are the most common venues by cities.

From that we know what kind of business are acclaimed by the customers.

The data will be provided by the Foursquare API.

The endpoint used will be: 
- https://api.foursquare.com/v2/venues/explore?

It returns all the venues by categories by city.

Example of a response: [{
    city: Bayonne, 
    latitude: 43.493338, 
    longitude: -1.475093, 
    venues: Chocolat Cazenave
    category: Tea Room
}, ...]

# Methodology

## Data exploratory

We explored the data by plotting a treemap of the venues by city.

This allowed to see which city had the most venues.

For example, we saw that Abu Dhabi had far less venues than the other cities so we assumed that was not consistent 
to compare Abu Dhabi with the other cities.

Thanks to the highchart framework, the treemap allowed us to drilldown and see the most popular categories by cities.

We also noticed that there were hundreds of categories of venues so we decided to keep the top 10 by city.

## Data transformation

We performed a one-hot encoding to be able to use the data in the model.

Indeed, we needed to convert the categorical features to numerical features but we did not want to apply a number to 
every category because that would have created a notion of distance.

If you set italian restaurant to 1, russian restaurant to 2 and french restaurant to 3, then you imply that a russian 
restaurant is more similar to an italian restaurant than a french one.

By using one-hot encoding, we convert categorical to numerical values without implying any distance or judgment.

## Statistical and ML analysis 

We used a k-mean with 10 clusters to cluster the cities by simimlarity according to their venues and plot them on a map.

The k-mean is convenient because it : 
- lets you decide the number of cluster
- relatively simple to understand,
- scales to large data sets, 
- guarantees convergence, 
- can warm-start the positions of centroids, 
- easily adapts to new examples, 
- generalizes to clusters of different shapes and sizes, such as elliptical clusters.

## Result

When plotting the results on the map, we found out that the clusters were grouped according to their geography.

This is amazing because it emphasizes the cultural difference.

Mediterranean countries such as Spain, France, Italy have a great number of restaurants but Rome is specific with a lot 
of historic sites.

Arabic countries have a lot of convenience stores and fat food (fast-food, yoghurt shops etc).

Northern countries have pubs, bars and live-music.

Capitals have more hotels and smaller town are more healthy with many gyms and pharmacies.
