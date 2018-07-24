# Airbnb-project

In this project we will explore an LA Airbnb dataset (that can be found in: http://insideairbnb.com/get-the-data.html) to try to understand what features drive revenue in the Airbnb rental business. Ultimately, our goal is to find what makes a listing successful and to help Aibnb hosts with useful insights. The full project is contained in the jupyter notebook: https://github.com/prodillo/Airbnb-project/blob/master/Python_Project_Final.ipynb 

![picture](https://github.com/prodillo/Airbnb-project/blob/master/Listings_clsutered.PNG)

**Findings**

**1. Amenities** 

**Summary**: Having Kitchen, Washer and Dryer increases the chances of success.

![picture](https://github.com/prodillo/Airbnb-project/blob/master/RF%20plot.PNG)

Based on the first plot we can say that Dryer, Kitchen, Cable TV, Elevator, Air conditiing and Washer are the most important amenities to define the success of a listing.

If we look at the second one, we can see that those listings that include Dryer, Kitchen and Washer are the ones with the highest difference in success rate. We can observe that the proportion of succeful listings having Kitchen is more than 40% higher than the proportion of succesful listings not having Kitchen. Similarly, the differnce for listings including Dryer is around 25% and for the listings including Washer is also around 25%.

Suprinsigly, the proportion of succesful listings including Air conditioning is 3% less than those listings including Air conditioning.

Now, let's see what happens with those listings that have Kitchen + Washer + Dryer, or Washer + Dryer or just Washer compared to those that does not include the corresponding combination:

![picture](https://github.com/prodillo/Airbnb-project/blob/master/Table.PNG)

We can see that the proportion of successful listings increase in 57.53% for those listings that include Kitchen + Washer + Dryer compared to those that do not have any of those amenities.

It is interesting to note that the proportion of successful listings increase in 26.06% for those listings that include Washer + Dryer compared to those that do not include those amenities. These amenities are easy to install and inexpensive and could be a way to imporve the chances of being succesful.

**Insight** 

Based on our results we can recommend the following:

- For those that are interested in entering into the Airbnb rental business, having Kitchen, Washer and Dryer or Washer and Dryer, is an important factor for the success of the business.

- For those that are already in the business and don't have those amenities, check the factibility of installing all or some of them.

**2. Sentiment** 

**Summary:** Not having reviews is not a problem at all

In this section we will explore how sentiments associated to reviews are related to success.

When we trained the Random Forest Classifier we could see that sentiment_nltk was an important feature in the tree, that give us a clue that we could find some finding relating sentiment and success:

![picture](https://github.com/prodillo/Airbnb-project/blob/master/Sent%20Plot.PNG)

Based on this we can conclude:

- Listings with negative average sentiment reviews are definitely less likely to be successful
- Listings with strong average positive sentiment are definitely more likely to be successful
- What is happening with the (-0.001 0.25] bin ?:
  -  97% of the listings in this category don't have any reviews
  -  The surprising thing is that based on this data, listings without reviews are more likely to be sucessful than those that has a moderate positive sentiment
  
**Insight** 

Unless Airbnb hosts are pretty sure that they will get strongly positive reviews, not having reviews is not a problem at all. This is helpful to all those hosts that might think that not having reviews could hurt their chances of success. Therefore, reviews should be encouraged by hosts only if they are confident that guests will write very good reviews.

**3. Location**

**Summary:** If you are interested in entering into the Airbnb business or if you want to expand your Airbnb business, look for Sunset Park and Playa del Rey area.

In this section we will explore what locations might be good to run an Airbnb listing.

![picture](https://github.com/prodillo/Airbnb-project/blob/master/Listings_clsutered.PNG)

Based on the clustering results, we identified the clusters 2, 10, 11 and 13 as clusters with a high average occupancy rate (above 50%) and high rating score (above 90). Also we identified clusters 8 and 18 as clusters that in average have good occupancy rates, are low priced, but most of them don't have rating scores. In order to visualize these cluster, we will define the variable 'most_competitive' to identify listings that belong to those clusters.

- Listings belonging to to clusters 2, 10, 11 and 13 will take the value of 1
- Listings belonging to to clusters 8 and 18 will take the value of 0.5
- All other listings will take the value of zero

Zones with a high concentration of listings belonging to the clusters mentioned before, will be considered as highly competitive areas and the objective of the plots that will come later is to visualize those areas in order to find good potential places to locate an Airbnb listing.

The next plot gives an overview of the listings in our dataset, Red and Green dots identify competitive areas. Looking at the map we can see how competitive is the Airbnb business in LA.

![picture](https://github.com/prodillo/Airbnb-project/blob/master/LA_overview.PNG)

Exploring the map, we noticed that surprinsigly there is an area in Santa Monica called Sunset Park, close to the airport, and close to Ocean Park, that is less dense in terms of the competitive listings available and therefore could be a good area to run an Airbnb listing.

![picture](https://github.com/prodillo/Airbnb-project/blob/master/Location1zoom.png)

Exploring further, we also noticed that Playa Vista area, next to Santa Monica, is also close to one the most demanded areas in LA and is less dense in terms of competitive listings available. This also could be a good place to run an Airbnb listing.

![picture](https://github.com/prodillo/Airbnb-project/blob/master/Location2zoom.png)

**Insight**

Using this interactive map, we were able to recommend two places to explore for the hosts interested in expanding their Airbnb business or are thinking about entering to the business.

Sunset Park and Playa Vista are next to highly demanded areas but are less overcrowded than those areas .Hence, these could be interesting places to locate an Airbnb listing.

This tool that we designed can be shared with those who might be interested in making further explorations of the LA Airbnb business and can be complemented with more data in the future.
