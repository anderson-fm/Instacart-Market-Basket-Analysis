# Instacart Market Basket Analysis

### Anderson Alves

#### *August, 2021*

This 2 week project was done as part of the course <i>Machine Learning with Python: Zero to GBMs</i>, a 6 week course lectured by Aakash N.S., and hosted on <a href="https://jovian.ai">Jovian.ai</a>.

The Zero to GBMs course focuses on supervised machine learning, decision trees, and gradient boosting using Python and its ecosystem of ML libraries: scikit-learn, XGBoost, and LightGBM.

For this course project I have selected the **Instacart Market Basket Analysis**, a <a href="https://kaggle.com">Kaggle.com</a> competition, to perform data cleaning & feature engineering as well as training, comparing & tuning machine learning models to create a recommendation system to predict future behavior of users based on the provided data.

# 1. Business Problem <br>

<div style="text-align:justify">This dataset comes from a competition hosted by Instacart on Kaggle. Instacart is a company that operates a grocery delivery and pick-up service. It allows customers to order groceries from multiple retailers and the shopping is done by a personal shopper. The service has a recommendation feature that suggests to the users some items that they may buy again when making a new order.<br>

In this competition, Instacart challenged the Kaggle community to use the provided anonymized data on customer orders over time to predict which previously purchased products will be in a user's next order.

Recommendation systems are now frequently used by online businesses. They use these systems to improve shopping potential and increase user interaction, allowing them to maximize their return on investment (ROI) based on the information gathered from customers' purchases and preferences. The knowledge-based Recommender System used by Instacart is an essential tool for those purposes by individually presenting more relevant products to each user.  </div> 


## 1.1 Dataset Content

The dataset contains about 3.4 million grocery orders from 200 thousand Instacart users. The data is distributed among 6 csv files and a submission sample:
 - aisles
 - departments
 - orders
 - order_products__prior
 - order_products__train
 - products
 - sample_submission
 
Each order is evaluated as prior, train, or test. Prior orders are the past behavior of the users while train and test orders represent the future behavior that we need to predict. Each user is divided between the train and test groups, and all of them have information on the different products purchased in all of their prior orders.

For the train category, the reordered products are already described, and we will use those to train a classification model to predict the products of the orders from the test category that are going to be reordered.

## 1.2. Solution Strategy
My strategy to solve this challenge was:

**Step 01.** Obtain and unpack the data from the source. <br>
**Step 02.** Data Description and Filtering. <br>
**Step 03.** Exploratory Data Analysis. <br>
**Step 04.** Feature Engeneering. <br>
**Step 05.** Data Preparation. <br>
**Step 06.** Feature Selection. <br>
**Step 07.** Machine Learning Modelling: XGBoost & LightGBM. <br>
**Step 08.** Parameter Tunning. <br>
**Step 09.** Evaluate Models Performance. <br>

# 2. Data Insights
**Hypothesis 01**: Most of the orders are made during the morning. <br>
**False**. On average, 52.7% of the orders of the day are made during the afternoon (12pm-6pm), while only 41.1% are made in the morning (6am-12pm). <br>
**Hypothesis 02**: Most of the orders are repeated weekly. <br>
**True**. It's observed that most orders are repeated after 7 days. The weekly pattern also shows in 14, 21, and 28 days. <br>
**Hypothesis 03**: The bestseller items are non-perishable foods. <br>
**False**. The overall top 10 bestsellers items are all from the produce aisle, with the most ordered being Bananas. <br>

# 3. Machine Learning Model Applied
Both XGBooster and LightGBM models were used in this project. <br>

# 4. Machine Learning Model Perfomance
The models' performance was analyzed by creating a baseline prediction and evaluating its Kaggle score result in the competition.
Then later comparing the models' predictions scores to the baseline. <br>

|Model | Kaggle Score | Increase from Baseline |
| :---: | :---: | :---: |
|Baseline (Repeat Last) | 0.21671 | - |
|XGBoost (Default) | 0.37890 | 74.84% |
|XBGoost (A Params) | 0.38074 | 75.69% |
|XBGoost (B Params) | 0.38090 | 75.76% |
|LightGBM (Default) | 0.38573 | 77.99% |
|LightGBM (A Params) | 0.38495 | 77.63% |
|LightGBM (B Params) | 0.38528 | 77.79% |

# 6. Conclusions

From the results we can visualize that the highest Increase from Baseline was obtained by using the LightGBM models, with an average of 77.8% increase from the baseline and an increase about 2% higher than the obtained with the XGBoost models.

# 7.  Next Steps

Evaluate the influence of the recommendation systems to the business.

# 8. References

In this work, multiple libraries and projects were consulted and used as reference. <br>
The following list comprises the most relevant ones that should provide further insights on the subject.

https://www.kaggle.com/fabienvs/instacart-xgboost-starter-lb-0-3791/code <br>
https://www.kaggle.com/paulantoine/light-gbm-benchmark-0-3692/code <br>
https://www.kaggle.com/nickycan/lb-0-3805009-python-edition/notebook <br>
https://www.kaggle.com/rshally/instacart-lb-392-runs-on-kaggle-with-2nd-clf/notebook <br>
https://www.kaggle.com/kokovidis/ml-instacart-f1-0-38-part-two-xgboost-f1-max <br>
https://www.kaggle.com/hongweizhang/how-to-calculate-f1-score/notebook <br>

https://towardsdatascience.com/a-look-at-precision-recall-and-f1-score-36b5fd0dd3ec <br>
https://towardsdatascience.com/an-exhaustive-list-of-methods-to-evaluate-recommender-systems-a70c05e121de <br>

### Acknowledgements

The dataset was provided by Instacart and its data was downloaded from  <a href="https://www.kaggle.com/c/instacart-market-basket-analysis/data">Kaggle's data bank</a>.
