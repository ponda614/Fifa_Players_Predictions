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
