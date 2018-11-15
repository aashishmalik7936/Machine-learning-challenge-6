# Machine learning challenge #6
I have finished on 59th rank out of 7542 participants. The competition was hosted by hacker Earth.

The training files were quite large so, I am dropping the link to downloas the dataset:
https://he-s3.s3.amazonaws.com/media/hackathon/machine-learning-challenge-6-1/predict-the-energy-used-612632a9-3f496e7f/a490e594-6-Dataset.zip

# Approach:
1. First I analysed the train file and found that only two columns had empty columns but the null values were less than 5% of total values    in those columns then I filled the null values with that value which occured the most becaue the columns were categorical and very few      null columns does not impact much on the model.

2. Then I did some EDA using kernel density plots and tried to find some insights.

3. For feature engineering, I tried to pair the columns with municipality id and other id's. But only municipality id worked and I got a      significant rise in accuracy. I also made some columns by applying some conditions accoring to problem statement and it helped in rising    the accuracy but not much.

4. I had used lightgbm model through out the competition, just used random forest and logistic regression in initial stages.

5. Initially, I was putting the hyperparameters of lightgbm manually but then I found an amazing library named scikit-optimize and this        library works similar to bayesian optimization. With the help of this library I found the best set of hyperparameters and I got a          significant boost in accuracy by doing this.

6. Finally, I dropped the least important features from the dataset because high dimensionality is not encouraged by any machine learning      model. I used lightgbm to find the feature importances. This also gave me a little amount of boost to accuracy.

# Things that could be tried:
1. I couldn't try xgboost and other boosting algorithms because they were taking a lot of time and computational power.

2. Stacking of different models could be done using different seeds.

3. More feature engineering could be done by analysing the data more deeply.

4. 5-fold cross validation could be used to give model more robust but it need lot of computional power so, I couldn't try out this.
