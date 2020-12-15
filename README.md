# Exploring Avocado Data and Building Predictive Models
## Purpose and Goal:
Inspired by the popularities of avocado toasts among millennials, and finding skyrocketed prices on avocadoes at produce sections recently, I wanted to find out which cities in the U.S. provide the most reasonable prices for avocados and understand the market and trends better to hopefully benefit suffering millennials (including myself). I explored the data of prices and volumes of avocados sold in the major metropolitan areas, analyzed the costs at different cities and the correlation between the volume and prices, and built machine learning models to predict prices.

## Data:
Avocado price data includes observations from 2015 to 2018 and was originally extracted from Hass Avocado Board and downloaded from Kaggle website. The dataset covers the average prices, types (conventional or organic), and cities and regions where avocados were sold.

## Data Analysis:

### 1. Correlation between price and volume
I had a hypothesis of demand and supply, which means, in other words, that if the consumed volumes are higher, then the prices would be lower. The scatter plot I created, using matplotlib in Python libraries displays that it seems there is a trend for that direction. The Pearson correlation coefficient showed a small negative correlation (-0.225) between the average price and average volume consumption. Thus, there is an association between demand and supply, but that cannot explain everything about how the prices are structured. Having some outliers on the right side of the plot where some cities had the highest prices while the consumed volumes are limited. 

In the next series of analyses, I would dive deep into the data and testing hypotheses on how the network of the geography of consumption and production impact prices.

### 2. Ranking of cities by volume and price
Based on the below bar chart, surprisingly, Los Angeles consumes twice more than that of the second-highest volume cities, New York. The volume of the consumption of Los Angeles is astonishingly larger than any other city.

According to U.S. Department of Agriculture, in 2017, the world production of avocados was 5.9 million tonnes, led by Mexico with 34% (2.01 million tonnes) of the total. In the U.S., California is the major producer, accounting for 93 percent of U.S. avocado output. However, most of US consumption relies on imports from Mexico - 89% of the imports. Thus, the proximity to these areas could highly likely affect the prices of avocados.

In terms of prices, the below chart shows that the Northeast and Mideast are the most expensive areas for avocados. It is surprising that Hartford-Springfield, Connecticut was the most expensive city. Also, San Francisco is geographically not so far from the production regions, but it ranked very high, even higher than New York and other Northeastern cities.

This brings down to a hypothesis on one factor that drives up prices: transportation costs from main production areas/regions (Mexico, CA, etc.) is the major element to impact prices? This would explain why Harford and other Northeastern cities had the highest costs. Based on the report from the Department of Agriculture, this could be strongly backed by their study for other fresh produce. The results of the "study indicate that transportation costs significantly increase the costs of marketing these produce items and therefore their wholesale price." 

The next question here is if living costs could be another major factor, considering some cities such as San Francisco where the proximity to Mexico would not be an issue, also ranked very high. Clearly, San Francisco could be an exception for this "proximity" theory, and yet the cost of living index, paradoxically indicates that since some cities which did not normally register as expensive cities such as Hartford, Philadelphia, and Albany (all Northeastern cities) did rank higher for avocados, confirms the hypothesis that the proximity to Mexico and South America may matter to the pricing.


### 3. Volume and price fluctuation (Time Series Analysis)
The below graph shows that there was a huge drop in the price in the summer, 2015. In general, it fluctuates over seasons - in summer, it goes down and in winter, it goes up. However, as a general trend, the plot shows that it is steadily increasing over years. And in 2017 there was a tremendous increase in the prices.

It is interesting to compare these ups and downs with those of the volume. In a sense, the volumes and prices are the flip sides of coins - the volume goes up strikingly high at the beginning of spring, and in summer, there is a smaller uptick and these are reflected on the price chart as downtimes. And that was explained in the first test on the Pearson correlation coefficient. There is a smaller association between the volume and price. Therefore, when there are more avocados in the market, the prices go down, and when there are not enough, the price increases.

### 4. Conventional vs Organic
Expectedly, the prices of organic avocados usually run higher than conventional ones. For some cities and regions such as Phoenix-Tuscon, West Texas, and New Mexico, compared with other cities, organic avocados are priced so much higher than the conventional ones.


## Machine Learning Models
### 1. Model building
For the predictive models, I used the following 5 models to train the datasets, test the predicted prices, and compared them against actual prices to score the accuracies. 

- Ensemble Model; Combined the following 4 models
- 2 Random Forest Models; Used different parameters respectively for version 1 and 2
- XGBoost
- Linear Regression

### 2. Accuracy scores
Based on the below chart, one Random Forest model did quite better than other models including the ensemble model in which I combined all four models' outputs and averaged them out. I used mean squared error, root mean squared error, and R2 (coefficients of determinations) to compare the accuracies and in all three measures, Random Forest 1 did the best.  (The scores were cross-validated. You can see my codes here.) 


## Conclusion and next steps
This study showed that there are some associations between prices and volumes. Additionally, the proximity to the major production region (Mexico) and seasons can be strong elements that affect the pricing. However, there are exceptions too. For example, you could move to Texas to buy cheaper avocados, but there is a possibility that organic avocados may not be as reasonably priced as conventional avocados. Additionally, although San Francisco is relatively closer to Mexico, that does not help you so much if you are trying to make avocado toasts every day.

As a next step, I would find more datasets that can be incorporated into models to predict more accurately such as volumes imported from Mexico, fuel prices to account for transportation costs and distances to the production area.

