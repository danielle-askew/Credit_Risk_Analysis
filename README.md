# Credit_Risk_Analysis
In this project, we use Python to build and evaluate several machine learning models to predict credit risk.
Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we oversampled the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Next, we used a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Lastly, we compared two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 

## Deliverable 1: Use Resampling Models to Predict Credit Risk
### Oversampling
RandomOverSampler Model  will randomly select from the minority class and the add it to the training set until both classifications are equal. 
Our results showed: 
* Classified 51,366 records each as High Risk and Low Risk.
* Balanced Accuracy = 66%
* The high_risk precision is about 1% only with 62% sensitivity, which makes a F1 of 2% only. 
* the low_risk population, has a precision of almost 100% with a sensitivity of 68%.

![oversampleclass](https://github.com/danielle-askew/Credit_Risk_Analysis/Images/RandomOverSampler_Model.png)
  
 ## SMOTE 
SMOTE, Synthetic Minority Oversampling Technique Model,  is similar to RandomOverSampler. It increases the size of the minority class by creating new values based on the value of the closest neighbors to the minority class instead of random selection.
 
![oversampleclass](https://github.com/danielle-askew/Credit_Risk_Analysis/Images/SMOTE_Model.png)

The results are pretty similar to the previous model.
* The balanced accuracy score is 65.6%.
* The high_risk precision is about 1% only with 63% sensitivity, which makes a F1 of 2% only.
* The low_risk population's precision is almost 100% with a improved sensitivity of 69%.
 

### Undersampling
In this section, we tested undersampling algorithms to determine which algorithm results in the best performance compared to the oversampling algorithms above. We undersampled the data using the Cluster Centroids algorithm.

* The "High Risk" precision rate was only at 1% with the recall at 69% giving this model an F1 score of 1%.
* The "Low Risk" precision rate was 100% and with a lower recall at 40% compared to the oversampling models.

![undersampleclass](https://github.com/danielle-askew/Credit_Risk_Analysis/Images/Undersample_Model.png)

## Deliverable 2: Use the SMOTEENN algorithm to Predict Credit Risk
In this section, we tested combination over- and under-sampling algorithm to determine if the algorithm results in the best performance compared to the other sampling algorithms above. We resampled the data using the SMOTEENN algorithm. 

### Combination Sampling
* The model showed 68,460 records as High Risk and 62,011 as Low Risk.
* Our balanced accuracy score improved to 64.5% when using this combined sampling model.
* The "High Risk" precision rate did not improve however and was only 1%. The recall rate did increase to 72%, which gives this model an F1 score of 2%.
* The "Low Risk" precision rate was 100% with the recall at 57%.

![combosampleclass](https://github.com/danielle-askew/Credit_Risk_Analysis/Images/Combo_Model.png)

## Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk
In this section, we compared two ensemble algorithms to determine which algorithm results in the best performance. We used the Balanced Random Forest Classifier and an Easy Ensemble AdaBoost classifier.

## BalancedRandomForestClassifier Model, two trees of the same size and equal size to the minority class are constructed to represent one for the majority class and one for the minority class.

* The models showed 51,366 as High Risk and 246 as Low Risk.
* The balanced accuracy score has increased to 78.9% for this model.
* The "High Risk precision rate has increased to 3% and a recall at 70% giving this model an F1 score of 6%.
* The "Low Risk" had a precision rate of 100% and the recall at 87%.
* With the top feature by importance showing as "total_rec_prncp" at 7.9% of the total.

![Ensemblesampleclass](https://github.com/danielle-askew/Credit_Risk_Analysis/Images/RandomForest_Model.png)

## EasyEnsembleClassifier Model, a set of classifiers where individual decisions are combined to classify new examples.

* We can see that the balanced accuracy score increased to 93.2% with this model.
* Our "High Risk precision rate increased to 9%. The recall rate as at 92% giving this model an F1 score of 16%.
* Our "Low Risk" had a precision rate of 100%. The recall rate showing at 94%.

![Ensemblesampleclass](https://github.com/danielle-askew/Credit_Risk_Analysis/Images/EasyEnsemble_Model.png)

# Summary
Reviewing all six of our models, we can see that our EasyEnsembleClassifer model had the best results in predticing  the "High Risk" candidates. The accuracy showed a rate of 93.2% and a 9% precision rate. The sensitivity rate displayed 92%, which was higher compared to the other models. 
When looking at the "Low Risk" category the sensitivity rate at 94% and an F1 score of 97% which was the highest out of the other models. Being that we got the highest results from this model, it is clear we would recommend to use this as the type of analysis.
