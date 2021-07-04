# Credit_Risk_Analysis

## Purpose
The purpose of this project is to evaluate 6 different ML techniques to determine which is most useful at prediciting a risky loan applications.  The six algorithms are:
1. RandomOverSample- over samples the minority classes by resampling actual data points
2. SMOTE- creates synthetic samples generated from the minority class.
3. Clustered Centroids- utilizes undersampling of the majority class by creating centroids near existing data to sample
4. SMOTEENN- utilize both SMOTE to oversample then applies nearest neighbor to reduce and balance sample populations
5. BalancedRandomForest - Randomly under-samples each bootstrap sample to balance it.
6. EasyEnsembleClassifier- an ensemble of AdaBoost learners .

### Results

- RandomOverSample model boosted the samples from the initial 51352 samples for both classes.  The original high risk class had only 347 samples.  The balanced accuracy of this model is only 64%, slightly better than a coin flip.  Precision for the High risk category is a paltry 0.01, recall is better but not stellar at 0.61.  See Figure 1.
![Figure 1](figures/figure_1.png)


- SMOTE - This model also increases the samples in the minority class to match that of the majority class.  The balanced accuracy of this model is only 62%, slightly better than a coin flip.  Precision for the High risk category is a paltry 0.01, recall is better but not stellar at 0.60.  These are slightly worse that the ROS algorithm.  See Figure 2. 
![Figure 2](figures/figure_2.png)


- Clustered Centroids This model undersamples the majority class to match the minority using clustering centroids. The balanced accuracy of this model is only 52%, basically a coin flip.  Precision for the High risk category is a paltry 0.01, recall is better at 0.60.  See Figure 3.
![Figure 3](figures/figure_3.png)


- SMOTEENN- This model combines oversampling of SMOTE with nearest neighbor to reduce samples.  The balanced accuracy of this model is only 65%, moderatelty better than a coin flip.  Precision for the High risk category is a paltry 0.01, recall is better at 0.71.  See figure 4.
![Figure 4](figures/figure_4.png)


- BalancedRandomForest - The balanced accuracy of this model is 79%.  Precision for the High risk category is a paltry 0.04, recall is decent at 0.67. See figure 5.
![Figure 5](figures/figure_5.png)


- EasyEnsembleClassifier- The balanced accuracy of this model is only 93%, the best of the group.  Precision for the High risk category is still a paltry 0.07, recall is the best of the group at 0.91.  See figure 6.
![Figure 6](figures/figure_6.png)

*** Summary Table ***
| Model | Accuracy | Precision | Recall |
|-------|----------|-----------|--------|
| ROS   | 0.643 | 0.01 | 0.61 |
| SMOTE | 0.620 | 0.01 | 0.60 |
| Clus.Cent| 0.516 | 0.01 | 0.60 |
| SMOTEENN | 0.649 | 0.01 | 0.71 |
| BRF | 0.788 | 0.04 | 0.67 |
| EEC | 0.925 | 0.07 | 0.91 |
### Summary

Although there was improvement with the ensemble models, The EasyEnsembleClassifier model had the best at identifying the highest recall rate.   Unfortunately all the models have a very high false positive rate which will result in denying credit to low risk customers.  None of the models did a good job of avoiding this because of the disparity of the precision, recall or F1 scores that would sufficiently identify high risk loans.  I would consider collecting additional data and maybe look at other types of data that might better correlate to high risk loan potential.