# Tennis_Win_Predictor

## Prjoect Overview:

* Created a model that predicts results of Men's proffesional tennis matches
* Data contained details of all the results of the last decade (2010-2020) sourced from Tennis-Data.co.uk
* Engineered features to improve prediction power. Such features included: win percentage,winpercentage for each each surface type and series type, average fraction of sets won, average game residual per set played.
* These features were calculated using results from the year prior to each data entry using a rolling window to update the statistics calculated for each match.
* Linear regresion classifer, Random Forest Classifier, Gradient Boosting Classifier and Deep Neural Network used to find the best performing model. 
* Deep Neural Netwowk provided the best performance with an accuracy of 75%
