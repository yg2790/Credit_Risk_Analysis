# Credit_Risk_Analysis
## Overview
Using six different supervised machine learning models to predict credit risks.

## Results
- Naive Random Oversampling </br>
Used the random oversampling method to train the dataset until the minority class and the majority classes are balanced. The balanced accuracy score is 64.9% accurate, meaning that it isn't very accurate. The confusion matrix and classification report showed that this model is not very accurate. The oversampled high risk data points showed extremely low precision and moderate sensitivity. However, low_risk data had 100% precision and around 70% sensitivity, meaning that it had a relatively higher False Negative results than to False Positive. </br>
<img width="738" alt="Naive Random Oversampling" src="https://user-images.githubusercontent.com/98621924/174480936-f0265e03-1d72-41bf-8a31-831a7244f70b.png"> </br>
- SMOTE Oversampling </br>
Synthetic minority oversampling technique (SMOTE) is when new instances are interpolated, meaning that its generated synthetically from numbers closest to its neighbors. THe balanced accuracy score for this model is around 61.6%. The confusion matrix and classification report showed that the results are even worse than the random oversampling results, with lower sensitivity for both high and low credit risk scores. </br>
<img width="735" alt="SMOTE Oversampling" src="https://user-images.githubusercontent.com/98621924/174481103-0fec713d-bb2c-4f76-bd4c-d7444e3ef996.png"> </br>
- Clustered Cemtroids Undersampling </br>
This model identifies clusters of the majority class, and generate synthetic points called centroids, representing the clusters, which allows the sampling down of the majority class to the minority class. This model has an even lower balanced score of 51%, with an f1 score of 0.01 for high risk and 0.6 for low_risk. </br>
<img width="724" alt="Clusterd Centroids" src="https://user-images.githubusercontent.com/98621924/174481195-c22f2ed2-0389-4451-b21e-006d369ee92f.png"> </br>
- SMOTEENN  </br>
This model combines the SMOTE and the Edited Nearest Neighbor(ENN) model, sampling both up and down. The first step is to oversample the minority class with SMOTE, and the second step is to clean the resulting data with an undersampling strategy. If the two nearest neighbors of a datapoint belong to two different classes, that data point is dropped. This model has an accuracy score of 0.64 and the highest sensitivity score yet to high_risk results of 0.7. However, there seems to be an trade off to its sensitivity to low_risk data points, resulting only in 0.58. </br>
<img width="726" alt="SMOTEENN" src="https://user-images.githubusercontent.com/98621924/174481377-b62e6341-9c47-4af1-b31d-e0ceabaf5d8c.png"> </br>
- Balanced Random Forest Classifier
This model has an drastically higher accuracy scor eof 0.7878 in comparison to the previous models, which might be due to the encoding of datapoints. The high_risk cluster now has 0.05 precision and 0.67 sensitivity, with an f1 score of 0.07, while maintaining a high sensitivity of 0.91 for the low_risk cluster. </br>
<img width="729" alt="Balanced Random Forest Classifier" src="https://user-images.githubusercontent.com/98621924/174481481-87c2b9e7-4e69-47a3-9394-95ca8ac65b1e.png"> </br>
- Easy Ensemble AdaBoost Classifier </br>
This model has the highest accuracy score of 0.85, and an f1 score of 0.12 for the high_risk cluster. The low_risk cluster has a 0.95 sensitivity in this model with an f-1 score of 0.97 This model's confusion matrix is the closest the testing data point with 66 True Positive out of 87, and 16199 True Negative out of 17118. </br>
<img width="748" alt="Easy Ensemble AdaBoost Classifier" src="https://user-images.githubusercontent.com/98621924/174481670-ad4d25d9-0697-4f8e-8606-fa945936a165.png"> </br>

## Conclusion
The Easy Ensemble AdaBoost Classifier is the most accurate out of the six models in predicting credit risks. This is due to that Adaptive Boosting models are trained and then evaluated. Allowing the room for correction and improvement before reaching the final ensembled prediction. 
