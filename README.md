## Problem Statement
**1)** Analyse the given data having user reviews and other information of restaurants. Perform an EDA to find out useful insights to improve overall restaurant experience in Bengaluru.

**2)** Build a recommendation system, where user should be able to express what he wants and system should recommend relevant restaurants, to his liking.

### EDA Findings and Approach

**1)	Distribution of ratings of restaurants in Bangalore.**

Very good quality restaurants in Bangalore, as most of the restaurants, have been rated between the range from 3 to 4.5.

**2)	How’s online order availability?**

Approximately 75% of the restaurant delivers online in Bangalore.

**3)	How many restaurants have a table booking option?**

Around 85% of the restaurants don't have a table booking facility.

**4)	Average Budget of restaurants in Bangalore.**

The majority of restaurants are pocket friendly and have an average cost below 1000 for 2 people. There is around only 75 restaurant which has the cost between 1500 and 4000.

**5)	The most favorite food of Bangaloreans.**

Pasta, Pizza, Cocktails, Mocktails, Burgers, Biryani, and Coffee are the most liked food in Bangalore.

**6)	Which are the most commonly served food items in Bangalore.**

Most of the restaurant serves a different variety of fried and other types of rice, but most favorite food item among Bangaloreans are Pasta, Pizza, Cocktails, Mocktails, and Burgers.
So including these favorite food items in their menu might increase their number of customers.

**7)	Most voted restaurants.**

Post Brew Pub, Church Street Social, Hoot and Meghana Foods, Hammered, Chutney chang, Koramangala Social, Vidyarthi Bhavan, Sotally tober are the most visited restaurants.

**8)	Highly and least rated restaurants.**

Belgian Waffle Factory, Biergarten, Hammered, You Mee, Toast & Tonic, Koramangala Social, The Terrace At Gilly's Redefined, Caperberry, Apsara Ice Cream And Smoke House Deli are highly rated restaurants.
Navya's, Shaadi Ki Biryani, Ammi's Biryani, Mast Kalandar, Meghana Biryani, Mamma Mexicana, Bageecha, Decker's Lane, Bageecha, Alibi - Maya International Hotel are least rated restaurants.

**Important Finding** - *Considering only rating is not the right measure of popularity, as there may be the case where one restaurant is rated 5 by few customers and another rated 4.8 by many customers.
So which one is better, the obvious choice is the second restaurant. Thus, we need to calculate the weighted rating using rating and number of votes.*

*To calculate the weighted rating we will use the weight factor and penalize rating with the formula*

*weighted_rating = weight_factor * aggregate_rating*



*where,
weight_factor is the total number of votes for any restaurant divided by max number of votes in the whole dataset (i.e. votes/max_votes)
aggregate_rating is the average rating for the restaurant.*

**9)	Top 10 most and least popular restaurants in Bangalore.**

Prost Brew Pub, Church Street Social, Meghana Foods, Hoot, Hammered,  Asala Hi A Social, Empire Restaurant, Chutney Chang,  Asala Hi Bhavan, Brooks, and Bonds Brewery are the most popular restaurants.

Real Ambur Dum Biryani, New Kudla Family Restaurant, Sri Rama, Cauvery Fast Food, Zodiac Grills, Spicy Andhra, Chamrajpet Kabab Junction,  Asala Daan, Ntr Café, The Paratha Stories are the least popular restaurants in Bangalore.


**Important Finding** - *There is a difference between the top 10 restaurants based on only rating and the top 10 based on overall popularity score. The latter one is more accurate, and Prost Brew Pub, Church Street Social, Meghana Foods, Hoot, Hammered, Koramangala Social is the most popular restaurants.

Also, there is some relation between the number of votes and the popularity of restaurants, as the top 5 most voted and top 5 most popular restaurants are the same.*


**10)	Type of restaurants available in Bangalore.**

The majority of the Bangalore restaurants are Quick Bites and Casual Dining type.

**11)	under what category most of the restaurants are listed?**

There are many options available for Delivery and Dine Out, but very few for Nightlife, Buffet, Cafes, Pubs, and bars. Thus, it will be a good idea to open restaurants of these categories with the help of further research about demand and locality.

**12)	Type of Cuisines available in Bangalore.**

There are many food varieties available in Bangalore, but the majority of the restaurant serves North Indian, South Indian, and Chinese.

**13)	Which area has the most number of restaurants?**

BTM and Koramangala mostly dominate in terms of the number of restaurants.

**14)	Explore area wise food specialty.**

No particular area specializes in any one kind of food, we can get all variety in each locality and North Indian, Chinese are most common in all localities.

**15)	For each category of restaurant, suggest the 'hottest' restaurant that received the most votes.**

Buffet - Vt Sindhur Veg, Cafes - Yomama!!, Delivery - Zengi Pub & Restaurant, Desserts - Wafl Co, Dine-Out - Zodiac Grills, Drinks & Nightlife - Xtreme Sports Bar, Pubs and Bars - White Horse

**16)	Major restaurant group.**

Apsara Ice Cream, Mcdonald's, Ramji Chaiwale, Brooks And Bonds Brewery, Lassi Shop, Pizza Hut, Petoo, Jigarthanda, Lakeview Milkbar, A2b - Adyar Ananda Bhavan are major chain restaurants available in Bangalore.

**17)	Whether rating depends on cost or not?**

There is not much dependency, however, we don't have any lower rating in a restaurant with an average cost of more than 1500. This means that most of the costly restaurant takes good care of their food and service

**18)	Whether a table booking facility dependent on average cost?**

Yes! the costlier restaurants mostly have a table booking facility.


### Recommender system approach

*	Combine name, rest_type, dish_liked, menu_item, category, and reviews.
*	Clean and normalize combined text
*	Filter restaurants are based on location, cost, and cuisine type provided by the user.
*	Then calculate cosine similarity between User Feels like (text) and combined text and store as similarity score.
*	Sort and return the top three restaurants based on similarity score and popularity score


**What can be done to improve the recommendation?**
*	The count and percentage of positive, negative reviews can be used for better recommendation results.
*	A more sophisticated formula like the Bayesian average can be used for calculating the popularity score, as the used formula is biased towards the number of votes.
*	For better recommendations, more advance methods like word embeddings or CountVectorizer can be used  for encoding text to vector (or feature extraction)
