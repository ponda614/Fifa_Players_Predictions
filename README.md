# Content
​
- [Google Slides Content link](https://docs.google.com/presentation/d/1H9v-q7bVhVsung7-6AhsWCUqByEli0z-hiUEGF9v5PQ/edit#slide=id.ge49a181691_0_1)
​
- Our topic will be FIFA World Players of 2019
​
- We will be working with FIFA_World_players_full_data.csv. The reason why we choose this dataset because it has a lot of features, the dataset contents allows us to apply the transformation mechanisms to a clean format, and we all have a common passion for the game. 
​
- The source of data if from Kaggle website, is a public web-based data-science environment. The FIFA_World_players_full_data.csv
​
- The question we want to answer are: 
​
	- Can team managers predict a player value prior to negotiations?
	- Does a contract of a player influence their performance?
	- What stats make a player more relevant to a position?
	- Are left-foot players more productive that than right-foot one?(possible removal)
​
# Communication Protocals 
​
- We are communicating through slack, zoom, and google drive.
​
# Machine Learning Model
​
- It has been recommended to use Random Forest smapling as model and we may also use other models to help us answer our questions. To support the model choosen we will Python, Scikit-Learn, and Imbalanced-learn.
​
## Database
​
- The Database we will use PostgreSQL, Amazon Web Services (AWS), and Psycopg2
​
## Description of preliminary data preprocessing
​
- The libaries we will be importing pandas, regex, matplotlib, and sklearn. With these libraries we will be cleaning the data and get it ready to upload to postgresSQL and AWS databases. 
​
## Description of preliminary feature engineering and preliminary feature selection, including the decision-making process.
​
- You can compute the standard correlation coefficient between each pair of attributes using the corr() method. Looking at all the correlations between each attribute will take up too much time, so we look at the attribute that correlates with the Rating value. 
​
- The correlation coefficient ranges from -1 to 1. When the correlation coefficient is close to 1, it means that there is a strong positive correlation.
​
- For the model we used ensemble Random Forest model. The concept of ensemble learning is the process of combining multiple models to help improve the accuracy and robustness, as well as decrease variance of the model, and therefore increase the overall performance of the model.
​
## Description of how data was split into training and testing sets?
​
- Separating data into training and testing sets is an important part of evaluating data mining models. Typically, when you separate a data set into a training set and testing set, most of the data is used for training, and a smaller portion of the data is used for testing. Analysis Services randomly samples the data to help ensure that the testing and training sets are similar. By using similar data for training and testing, you can minimize the effects of data discrepancies and better understand the characteristics of the model.
​
After a model has been processed by using the training set, you test the model by making predictions against the test set. Because the data in the testing set already contains known values for the attribute that you want to predict, it is easy to determine whether the model's guesses are correct.
​
## Explanation of model choice, including limitations and benefits?
​
#### Impressive in Versatility 
​
- Whether you have a regression or classification task, random forest is an applicable model for your needs. It can handle binary features, categorical features, and numerical features. There is very little pre-processing that needs to be done. The data does not need to be rescaled or transformed.
​
#### Parallelizable
​
- They are parallelizable, meaning that we can split the process to multiple machines to run. This results in faster computation time. Boosted models are sequential in contrast, and would take longer to compute. Side note: Specifically, in Python, to run this in multiple machines, provide the parameter “n_jobs = -1” The -1 is an indication to use all available machines. See scikit-learn documentation for further details.
 
#### Great with High dimensionality
​
- Random forests is great with high dimensional data since we are working with subsets of data.
Quick Prediction/Training Speed It is faster to train than decision trees because we are working only on a subset of features in this model, so we can easily work with hundreds of features. Prediction speed is significantly faster than training speed because we can save generated forests for future uses.
​
#### Robust to Outliers and Non-linear Data
Random forest handles outliers by essentially binning them. It is also indifferent to non-linear features.
​
#### Handles Unbalanced Data
​
- It has methods for balancing error in class population unbalanced data sets. Random forest tries to minimize the overall error rate, so when we have an unbalance data set, the larger class will get a low error rate while the smaller class will have a larger error rate.
​
#### Low Bias, Moderate Variance
​
- Each decision tree has a high variance, but low bias. But because we average all the trees in random forest, we are averaging the variance as well so that we have a low bias and moderate variance model.
​
#### Drawbacks
​
- Model interpretability: Random forest models are not all that interpretable; they are like black boxes.For very large data sets, the size of the trees can take up a lot of memory. It can tend to overfit, so you should tune the hyperparameters.
​
# Database stores static data for use during the project?
​
- PostgreSQL will used to house the data in raw format. We will create additional tables with full definition of player positions.
​
# Database interfaces with the project in some format?
​
- We will use psycopg2 library to intergrate with the database. 
​
# Includes at least two tables? 
​
- Look in notebooks for the tables. 
​
# Includes at least one join using the database language?
​
- We don't have one join because we do not need to make connection with any other tables.
​
# Includes at least one connection string?
​
- conn_string = "host="+ creds.pg_rds_endpoint +" port="+ "5432" +" dbname="+ creds.pg_db_name +" user=" 		+ creds.pg_user / +" password="+ creds.pg_pwd
