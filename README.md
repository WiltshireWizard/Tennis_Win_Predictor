# Tennis_Win_Predictor

## Prjoect Overview:

* Created a model that predicts results of Men's professional tennis matches
* Data contained details of all the results of the last decade (2010-2020) sourced from Tennis-Data.co.uk
* Engineered features to improve prediction power. Such features included: win percentage,winpercentage for each each surface type and series type, average fraction of sets won, average game residual per set played.
* These features were calculated using results from the year prior to each data entry using a rolling window to update the statistics calculated for each match.
* Linear regresion classifer, Random Forest Classifier, Gradient Boosting Classifier and Deep Neural Network used to find the best performing model. 
* Deep Neural Netwowk provided the best performance with an accuracy of 75%

## Data Cleaning and Feature Engineering:

* Created Columns for day, month and year.
* Created column for total sets played in each match.
* Null values for sets that weren't played filled with 0.
* Removed data entries for matches where there was a walkover, player retired or where a player was disqualified.
* Filled null values for rankings data witht he lowest possible ranking of 2000.
* Created columns for fraction of sets won and average game residual per set.
* Created tournament index using a for loop updating the tournamnet index everytime the tournament changes. The earliest tournamnet had an index of 0 and the most recent tournamnet has the highest index number.
* Aggregated data for each player within each tournament, using created features and the tournament indexes.
* Aggregated stats for each player across tournaments. A rolling window of a year prior to each tournament was used to get an indication of the players current form.
* In the rolling window, more features were created to improve predictive power of models. Such features included Win percentage, Win percentage per surface type and series type.
* Merged data calaculated in the rolling window with the available data like player rankings to build a predictive model. 

## Model Building:

First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.
I tried four different models and evaluated their performance using accuracy:
  * **Logistic Regression:** Used as a baseline for gauging performance.
  * **Random Forest Classifier:** Used as it deals well with colinearity in features which is unavoidable with this sort of data. (Win percentage is related to Ranking)
  * **Gradient Boosting Classifier:** With GridSearchCV used to optimize model. Used to see if it outperforms the Random Forest Classifier.
  * **Deep Neural Network:**  Input layer had 400 nodes, hidden layer 200 nodes and output layer 1 node all with dense connections. Dropout of 0.5 used in first 2 layers. 
                              Early stopping and model checkpoint used to ensure best performance of the model used.
                              
 ## Model Performance:
 
 * **Logistic Regression:** accuracy = 67%
 * **Random Forest:** accuracy = 69%
 * **Gradient Boosting Classifier:** accuracy = 72%
 * **Neural Network:** accuracy = 75%
 
 The best performance came from the neural network.
 With even more extensive feature engineering this performance could be further improved.
 Ideas for potential further features include: Tournaments Won, career high ranking and Player head to head stats.
 
 
 
 
