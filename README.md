|**`PROJECT TOPIC`**| **Our topic will be FIFA World Players of 2019**|
|--|--|
||We will be working with Fifa world players dataset that we found on Kaggle website, </br>is a public web-based data-science environment: FIFA_World_players_full_data.csv.</br>We chose this dataset because: <li>it appears complete, it lists lots of player features,</li><li>its content allows us to apply the transformation mechanisms and cleanse the data,</li><li>and we all have a common passion for the game that may translate into a diverse analysis.</li><li>Does height, weight, or agility make goal keeper more likely to stop penalty kicks? <li></li> Does height and agility make every player more likely to have area ball accuracy?<li>|
|**`Questions our analysis seeks to answer`**| |
||<li> What player stats are most relevant to their position? </li><li>Does a contract of a player influence their performance?</li><li>What stats make a player more relevant to a position?</li><li>How many players play on their weak foot ?(possible removal)</li>|
<p>
	
| **`GitHub ORGNIZATION`**| **`Main`**|**`Owner`**|**`Branches`**|**`URL`**|
|--:|:--|--|--|--|
| |notebooks| Leticia Neves |leticiabranch|https://github.com/ponda614/Fifa_Players_Predictions/tree/leticiabranch|
| |resources| Lamiley Suantah|Lambranch|https://github.com/ponda614Fifa_Players_Predictions/tree/Lambranch|
| |images|  Alex Vargas|AlexBranch|https://github.com/ponda614/Fifa_Players_Predictions/tree/AlexBranch|
| |  |Richard Dépestre|richardbranch|https://github.com/ponda614/Fifa_Players_Predictions/tree/richardbranch|
	
| **`Communication Protocols`**  | |
|--:|:--|
|  slack|will be used for team meetings, code reviews, collaborative coding |
|zoom|will be used to facilite all face to face meetings, collaborative tasks|
| google drive|[project schematics location](https://docs.google.com/presentation/d/1H9v-q7bVhVsung7-6AhsWCUqByEli0z-hiUEGF9v5PQ/edit#slide=id.ge49a181691_0_1) |
| **`Additional Communication Protocols`**||
|emails||
|mobiles||
| **`DATABASE`** | | | | | |
|--|--|--|--|--|--|
|**`local database:`**|PostgreSQL|**`cloud database:`**|AWS RDS|**`Protocol:`**|Psycopg2|
|**`storage`**|AWS S3||||||

| **`Machine Learning Model`**| |It has been recommended to use Random Forest smapling as model for this project.</br>To support the model chosen we will Python, Scikit-Learn, and Imbalanced-learn.||
|--|--:|--|--|
|  | | **`Preliminary data preprocessing`**| |
| |**`Pandas`**|<li> extract data from data base </li><li>remove undesirables data</li><li>encode text column content</li><li>regex</li>|
||**`Matplotlib`**|visualize data and make correction|
|||The libaries we will be importing pandas, regex, matplotlib, and sklearn. With these libraries we will be cleaning the data </br>and get it ready to upload to postgresSQL and AWS databases. |
|**`feature engineering`**| | | |
|**`feature selection`**| | You can compute the standard correlation coefficient between each pair of attributes using the corr() method.</br>Looking at all the correlations between each attribute will take up too much time, so we look at the attribute that correlates with the Rating value.</br>The correlation coefficient ranges from -1 to 1. When the correlation coefficient is close to 1, it means that there is a strong positive correlation.| |
|**`Decision-making process`**| | | |
|**`training and testing sets`**||Separating data into training and testing sets is an important part of evaluating data mining models.</br>Typically, when you separate a data set into a training set and testing set, most of the data is used for training,</br>and a smaller portion of the data is used for testing.</br>Analysis Services randomly samples the data to help ensure that the testing and training sets are similar.</br>By using similar data for training and testing, you can minimize the effects of data discrepancies </br>and better understand the characteristics of the model.</br>After a model has been processed by using the training set, you test the model by making predictions against the test set.</br>Because the data in the testing set already contains known values for the attribute that you want to predict,</br>it is easy to determine whether the model's guesses are correct.||
|**`model choice`**||For the model we used ensemble Random Forest model. The concept of ensemble learning is the process of </br>combining multiple models to help improve the accuracy and robustness, as well as decrease variance of the model,</br> and therefore increase the overall performance of the model.|
|| **`benefits`**|**<u>Impressive in Versatility</u>**</br>Whether you have a regression or classification task, random forest is an applicable model for your needs.</br>It can handle binary features, categorical features, and numerical features.</br>There is very little pre-processing that needs to be done. The data does not need to be rescaled or transformed.</p>**<u>Parallelizable</u>**</br>They are parallelizable, meaning that we can split the process to multiple machines to run. This results in faster computation time. Boosted models are sequential in contrast, and would take longer to compute. Side note: Specifically, in Python, to run this in multiple machines, provide the parameter “n_jobs = -1” The -1 is an indication to use all available machines. See scikit-learn documentation for further details.</p>**<u>Great with High dimensionality</u>**</br>Random forests is great with high dimensional data since we are working with subsets of data.</br>Quick Prediction/Training Speed It is faster to train than decision trees because we are working only on a subset of features in this model, so we can easily work with hundreds of features. Prediction speed is significantly faster than training speed because we can save generated forests for future uses.</p>**<u>Robust to Outliers and Non-linear Data</u>**</br>Random forest handles outliers by essentially binning them. It is also indifferent to non-linear features.</p><u>**Handles Unbalanced Data**</u></br>It has methods for balancing error in class population unbalanced data sets. Random forest tries to minimize the overall error rate,</br>so when we have an unbalance data set, the larger class will get a low error rate while the smaller class will have a larger error rate.</p>**<u>Low Bias, Moderate Variance</u>**</br>Each decision tree has a high variance, but low bias. But because we average all the trees in random forest,</br>we are averaging the variance as well so that we have a low bias and moderate variance model.|
|| **`limitations`** |Model interpretability: Random forest models are not all that interpretable; they are like black boxes.</br>For very large data sets, the size of the trees can take up a lot of memory. It can tend to overfit, so you should tune the hyperparameters.|
|**ANALYSIS**||
|--:|--|
| |**`Analysis Of Data`**|Defenders are the 3-4 back players who are skilled at standing tackle, marking interceptions, ball control.
Midfielders are the connecting strings of the team with the primary objective of distributing passes to trigger attack on the opponent. They must be excellent at ball control, dribbling and short passes that can start attacks. 
Depending on the team strategy can be only one or 2 players primary role of creating goal scoring opportunities.  An attacker must be an accomplished penalty shooter, great dribbling, ball control and finishing are some the key skills. 

Correlation of skills with field position.
There are about 34 different skills sets that each player is rated on by field positions. We considered the most impactful skills on each field position by considering the correlation coefficients and the variability of the p-value < 0.05.
From the correlation matrix, there are both direct and inverse correlation of skills with overall impact on field position. Significantly impactful skill implied all dependent variables with p-value < 0.05. For example, some impactful skills for some field positions are:
*Penalty shooting, dribbling, ball control and finishing are impactful on a sticker position.
*Some impactful skills for midfielders are dribbling, ball control, short passing and penalty kicks.
*Defenders must be skilled in standing tackle, marking interceptions, ball control, aggression.

Predictive model
Some players with dominant skills were sampled to design a predictive model for a team. 
Data was split into training/test.
A linear regression model was initiated to establish relationship.
Random forest model was used to predict the best possible formation for a team based on the skills set of players.| 
	
|**`DATABASE INTEGRATION`**| |
|--:|--|
| | PostgreSQL will used to house the data in raw format.</br>We will create additional tables with full definition of player positions.|
|**`static data`**| When the project starts a module will run, connect to the database and load the content of our delimited dataset.</br>For more details follow this link: [load data to postgresql](https://github.com/ponda614/Data-Science-Final-Project-/blob/main/resources/s0_load_dataset_to_rds.ipynb)|
|**`DB to Project`**| We will use psycopg2 library to intergrate with the database. |
|**`Includes at least two tables`**|Look in notebooks for the tables. |
|**`DB joins`**| We don't have one join because we do not need to make connection with any other tables.|
|**`connection string`**|```conn_string = "host="+ creds.pg_rds_endpoint +" port="+ "5432" +" dbname="+ creds.pg_db_name +" user=" 		+ creds.pg_user / +" password="+ creds.pg_pwd```|
	
# Content
- [Google Slides Content link](https://docs.google.com/presentation/d/1H9v-q7bVhVsung7-6AhsWCUqByEli0z-hiUEGF9v5PQ/edit#slide=id.ge49a181691_0_1)
