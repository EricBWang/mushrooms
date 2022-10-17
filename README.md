# Mushrooms
This project seeks to explore mushrooms in regards to how their physical characteristics vary for edible and poisonous mushrooms as well as identify trends in the consumer market. This paper details the process involved and synthesizes my findings.
 
## Why Mushrooms?
 
**Nutritional Value**
“Mushrooms’ team of nutrients and health profile are ideal for a sports performance diet” and boosting one’s immune system by providing vitamin D to support strong bones, Potassium for muscle function and blood pressure control, B vitamins to provide energy and support metabolism, etc. Furthermore, they’re low in calories and are fat, cholesterol, and gluten-free, assisting with weight management (1). Mushrooms are also rich in Niacin or Vitamin B3, a nutrient shown to improve mood disorders by assisting in the formation of serotonin (2).
 
**Sustainability**
Considered one of the most sustainably produced foods in the U.S., a pound of mushrooms only require 1.8 gallons of water, a fraction of water inputs required for other foods. In addition, a pound of mushrooms only uses 1.0 kwh of electricity, generating only 0.7 pound of CO2 equivalents. They also require a very small amount of land to grow, with 1 acre being able to grow 1 million pounds of mushrooms (3)!
 
**Unique Flavor Profile**
“Described as a savory, brothy, rich, or meaty taste sensation,” Umami is the fifth basic taste after sweet, salty, bitter and sour (4). It enables flavor enhancement, counterbalances saltiness, and highlights sweetness while lessening bitterness.
 
## Dataset 1: Exploring Edible vs. Poisonous Mushrooms
Comprised of 173 mushroom species from 23 families, my data consists of different mushroom’s physical characteristics (i.e. cap diameter, stem height, odor, etc.) and growth characteristics (i.e. habitat, season).
 
## Exploratory Data Analysis
I examined feature distributions via histograms and summary statistics. In addition, I looked at respective feature correlations both amongst the features and with the target class using three different correlation metrics: Pearson Coefficient, Point Biserial Correlation, and Theil’s U (Uncertainty Coefficient). Based off my analysis, I found multicollinearity between cap diameter and stem width, alongside minimal correlation between any features and the target class. 
 
## Model Approach and Results
I decided to implement Random Forests as the algorithm is robust to outliers, doesn't require feature scaling, and doesn't make any formal assumptions regarding feature distributions. It also handles skewed data and multi-modal data as well. Outliers, differently scaled features, and skewed / multi-modal distributions were all factors discovered during the exploratory data analysis portion of this project. 

For the sake of predicting a mushroom's edibility, I decided to utilize both accuracy and sensitivity as my metrics for evaluating model performance. This is to balance between maximizing the total number of right predictions as well as reduce the number of false negatives (predicting poisonous mushrooms as edible) predicted by the model.

**Results**
100% Accuracy and 100% Sensitivity across both train and test data sets. 
 
## Findings and Recommendations
After further research done on a previous iteration of my dataset, I found that odor was a strong predictor for a mushroom’s edibility, with a correlation of 91%. However, this feature was not present in my version of the dataset so I did not explore this further. 

Otherwise, there were no were no significant predictors for a mushroom’s edibility. This suggests that it’s a function of most, if not all of the characteristics present in the dataset. In other words, besides a mushroom’s odor (which is still a bit ambiguous), it’s hard for a non-expert lacking further domain knowledge to determine if a mushroom is safe to consume or not! 
 
## Model and Data Limitations
Many of a mushroom’s physical characteristics are correlated such as cap shape and surface as they age. More specifically, mushrooms tend to have convex/smooth surfaces when they are young while becoming more flat and dry as they grow older. Such an issue can be addressed by extending the data to create entries for different stages of a mushroom species’ lifespan. In addition, the data is low-dimensional, resulting in an inadequate representation of a mushroom’s characteristics. For instance, there are only 12 colors describing a mushroom’s cap color, which is vague and ambiguous. Employing image classifiers to extract a more robust depiction of a mushroom would remedy this issue. Finally, many classification algorithms such as the Random Forest model that I utilized require lots of computation power. To mitigate this challenge, I would use cloud processing in the future. 
## Dataset 2: Exploring Edible Mushrooms in Consumer Markets
I researched findings developed based on a dataset from the USDA National Agricultural Statistics Service, consisting of elements such as area, production, volume of sales, price per pound, value, number of mushroom growers, etc. These studies and corresponding datasets can be found at https://www.mushroomcouncil.org/.

## Findings
In regards to the retail industry, clear continued growth in dollar sales has stayed consistent across 2014-2018, with % changes of +2.8, +3.8, +3.9, +4.2, +5.4, respectively. Diving deeper into individual retail channels / segments, the channels can be split into mass/super, club, dollar, grocery, and all other categories. Amongst these, the grocery channel takes the majority share of mushroom purchases in 2018, making up 76% of the channel share. Studies have shown that the reasoning behind this is due to increasing public awareness of mushrooms’ numerous health benefits. While one may hypothesize or assume that there would be similar growth in the food service industry as well, this is not the case. In fact, there’s been a steady decline over the past decade in the frequency of mushroom related items introduced at the top 250 food chains in the U.S. 

## Next Steps
A natural next step in my analysis of these datasets would be to build models for inferential purposes, predicting any relevant key metric (i.e. price per pound, volume of sales, etc.). I would also consider exploring other components of the mushroom consumer market, such as production and shipping trends. I’d also like to dive deeper and research key drivers behind the growth trends in the retail segment. 

## Conclusions
Mushrooms are diverse. If you’re looking to pick out ones that are safe to consume, it’s quite a challenging task as a mushroom’s edibility results from many factors. Thankfully, we have experts and strong machine learning models! There are clear growth trends in volume and dollar sales of mushrooms in the retail industry over the past eight years, with grocery channels possessing the majority channel share. Despite this, there’s also been a decrease in the number of mushroom related items introduced in food service contexts. 
