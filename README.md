# Customer Analytics - Supermarket Segmentation: Project Overview 
* Created predictive models using Multinomial Logistic Regression and Linear Regession to predict probabilities relative to price elasticity. Probability including

1. Purchase Probability 
2. Brand Choice Probability 
3. Purchase Quantity

* Engineered features from the Encrypted customers data and purchases data including key features i.e. Sex, Martial status, Age, Income, Education, Occupation, Settlement Size, etc.
* Performed preliminary and descriptive analysis with Hierarchical Clustering and K-mean Clustering with PCA to understand customer segmentations in the data.

## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, json, pickle

## Data Normalization

 **Customer Data**
*	Sex
*	Marital status
*	Age
*	Education
*	Income
*	Occupation
*	Settlement size

 **Purchase Data**
*	Incidence (buy or not buy boolean)
*	Brand Quantity
*	Price
*	Promotion
*	Customer Data
*	Date


After loading raw data, I performed data normalization so that all features have equal weight. Otherwise feature, for example, Income would be considered much more important compared to Education.

## Segmentation via Clustering using Customer Data
This section is to perform segmentation to see how our customers can be grouped.
After normalizing the data, I performed clustering as a preliminary analysis of the data to see how the groups would look like from these algorithms

I tried tree different models:
*	**Hierarchical Clustering** – to get an idea of the ideal number of clusters
*	**K-mean Clustering** – after getting a decent idea of the expected clusters, perform K-mean to see how the groups result look like.
*	**K-mean Clustering with PCA** – to reduce number of features to only the most important ones.

![Hierarchicalresult](./Image/Hier.JPG)
![KmeanWCSS](./Image/kmeanwcss.JPG)
![Kmeanclusters](./Image/kmean.JPG)


## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 

![EDA1](./Image/EDA1.JPG)
![EDA2](./Image/EDA2.JPG)
![EDA3](./Image/EDA3.JPG)
![EDA4](./Image/EDA4.JPG)
![EDA5](./Image/EDA5.JPG)


## Model Building 

*	**Logistic Regression** - is used to calculate purchase probability relative to price elasticity.

Price Elasticity = % change in purchase probability / % change in price.

Inelastic, we increase the price of the product since it affects the probability of buying less than 1% per 1% price change.

Elastic, we decrease the price of the product since it affects the probability of buying less than 1% per 1% price change.

![purchaseprob](./Image/purchaseprob.JPG)

This way we know which products we should increase/decrease in price or add promotions to them

This can be done by customer segments/brands/etc.


