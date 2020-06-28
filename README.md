# Churn-Prediction-with-Spark

https://medium.com/@bengubanudonmez/how-to-predict-customer-churn-with-spark-adfc4aebf221

Developing ML models for prediction of Customer Churn of an imaginary digital music service Sparkify, by using Spark
1. Business Understanding
Sparkify is an imaginary popular digital music service similar to Spotify . User stream their favorite songs, even the free tier that place advertisements between songs or using the premium subscription model where they stream music as free but pay a monthly flat rate.
Users can upgrade, downgrade or cancel their service at any time. So we need to make sure that users love the service.
Every time a user interacts with the service while they’re playing songs, logging out, visiting pages, getting errors, adding friend, adding playlist ,like in a song with a thumbs up, hearing an ad, or downgrading their service , it generates a user log data.
All this data contains the key insight for keeping users happy and not churn
In this project we are going to predict which users are at risk to churn either downgrading from premium to free tier or cancelling their service alltogether.
If we can accurately identify these users before they leave, we can offer them discounts and incentives, not to leave the service

2. Data Understanding
Acutal data set is 12GB, we will work on a small subset of these data which is 128MB
We will load and clean dataset with Spark, and perform some exploratory data analysis, after analysing data we will build out the features which seems promising to train our machine learning models on.
After importing necessary libraries, we create a Spark Session , and load data to a Spark data frame object.

3.Data Preparing
according to analysis there is no duplicate record and also no missing values in the userID or session columns
but there are userId values that are empty strings that needs to be filtered.
3.1.Exploratory Data Analysis
after doing basic manipulations and some preliminary analysis with pyspark, we need to define Churn to use as the label for our model.
in page column we see the activities of users, and we can set label as churn if user has activity Cancellation Confirmation = 1.
3.2.Feature Engineering
I ve decided to get some metrics as below to use in my ML models. I also calculated metrics from the page column which contains activities of the users.

4. Data Modeling and Evaluation
Since we are trying to classify data as churn or not, for modelling our data we can use classification methods of Spark MLlib:
Logistic Regression
Random Forest
Gradient Boosted Tree
Desicion Tree

5.Conclusion
In this project we applied CRISP-DM methodologies which are
understanding business , problem and needs, and then
understanding data with some manipulations and
for data preparation part with performing some exploratory data analysis and feature engineering,
in data modeling and evaluation part we created and evaluated our classification models that can be used for prediction of customer churn.
As a result the logistic regression model showed the highest performance with F1-Score:0.65 and accuracy:0.72 , on the other hand for the desicion tree clasifier F1 score showed a weaker performance.
These results were obtained with models that were trained and tested using the small subset of Sparkify dataset that only has 225 unique customers.
For the original dataset which has 12 GB size, feature engineering part can be enriched or further hyperparameter tuning may be needed for developing models to get higher scores.
