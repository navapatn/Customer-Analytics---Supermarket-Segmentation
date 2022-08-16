# Customer Analytics - Supermarket Segmentation: Project Overview 
* Created predictive models using Multinomial Logistic Regression and Linear Regession to predict
* 1. Purchase Probability 
* 2. Brand Choice Probability 
* 3. Purchase Quantity 
* Engineered features from the Encrypted customers data and purchases data including key features i.e. Sex, Martial status, Age, Income, Education, Occupation, Settlement Size, etc.
* Performed preliminary and descriptive analysis with Hierarchical Clustering and K-mean Clustering to understand customer segmentations in the data.

## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, json, pickle

## Data Normalization

*	Sex
*	Marital status
*	Age
*	Education
*	Income
*	Occupation
*	Settlement size

After loading raw data, I performed data normalization so that all features have equal weight. Otherwise feature, for example, Income would be considered much more important compared to Education.

## Segmentation via Clustering
After normalizing the data, I performed clustering as a preliminary analysis of the data to see how the groups would look like from these algorithms

*I tried tree different models:
*	**Hierarchical Clustering** – to get an idea of the ideal number of clusters
*	**K-mean Clustering** – after getting a decent idea of the expected clusters, perform K-mean to see how the groups result look like.
*	**K-mean Clustering with PCA** – to reduce number of features to only the most important ones.


## EDA
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 

![alt text](https://github.com/PlayingNumbers/ds_salary_proj/blob/master/salary_by_job_title.PNG "Salary by Position")
![alt text](https://github.com/PlayingNumbers/ds_salary_proj/blob/master/positions_by_state.png "Job Opportunities by State")
![alt text](https://github.com/PlayingNumbers/ds_salary_proj/blob/master/correlation_visual.png "Correlations")

## Model Building 

*	**Logistic Regression** - is used to calculate price elasticity of purchase probability.

Price Elasticity = %change in purchase probability/%change in price.

Inelastic, we increase the price of the product since it affects the probability of buying less than 1% per 1% price change.

Elastic, we decrease the price of the product since it affects the probability of buying less than 1% per 1% price change.

## Model performance
The Random Forest model far outperformed the other approaches on the test and validation sets. 
*	**Random Forest** : MAE = 11.22
*	**Linear Regression**: MAE = 18.86
*	**Ridge Regression**: MAE = 19.67

## Productionization 
In this step, I built a flask API endpoint that was hosted on a local webserver by following along with the TDS tutorial in the reference section above. The API endpoint takes in a request with a list of values from a job listing and returns an estimated salary. 


