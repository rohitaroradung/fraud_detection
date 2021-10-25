# fraud_detection

ABSTRACT


In this project, I have developed a ML model to identify fraudulent credit card transactions based on number of features. The dataset for this problem has been taken from Kaggle which contains Features V1, V2, … V28 which are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions. Given the imbalance ratio of two classes, Confusion matrix accuracy of models is not good evaluation matrix for different ML models. Instead of Confusion matrix accuracy, I measured performance based on precision recall curve and AP score and to break ties between different model, I used F-1 score and false positive.

First, I developed models without using any sampling techniques on training dataset, then I used different sampling techniques like random under sampling and oversampling with smote to balance the dataset and further develop models based on balanced sample training dataset.   
    

INTRODUCTION

Credit cards are useful financial tools that helps a individual to purchase a good that may or may not be necessary even when someone does not have enough money in their bank accounts to purchase that good unless the amount of good is below the limit sanctioned by bank. However, credit cards have huge interest rates after due date has been passed so any big purchase on credit card which individual cannot pay before due date is enough to make someone bankrupt or in continuous debt due to huge interest rates.

Due to convenience of credit cards and method of paying postpaid bills, it also become easy and huge profitable targets for scammers. Scammers can withdraw a significant amount can be without the owner’s knowledge and without any much risk involved, in a short period. Fraudsters always try to make every fraudulent transaction legitimate, which makes fraud detection very challenging and difficult task to detect.

Further, as number of fraudulent transactions is often very less in comparison to legitimate transactions, detection of fraud transactions using machine learning become very challenging as ML algorithms would be biased towards one class due to imbalance dataset. As if legitimate transactions are detected as fraud, it can bring huge losses to credit card company while on the other hand if fraud detection go undetected, it can make credit card holder financially unstable besides trust of the credit card holders on credit card can become less which would again eventually result in huge losses to credit card company.


Methodology

The following steps are followed for this project:
•	First, dataset is checked for null values and features has been scaled using standard scaler function.
•	Then dataset is split between train and test dataset in which test size is 40% of the total dataset
•	Then different ML models is trained on training dataset without any sampling techniques.
•	Further, random under sampling is applied on training dataset and then again different ML models is fitted on sample dataset
•	Then for oversampling techniques, new training dataset is prepared before applying different sample techniques in which rows belonging to non-fraudulent transactions is halved from original training dataset.
•	Then different smote techniques is used to oversample and different ML models is applied to all different oversample dataset.

Notebook organization

Based on problem analyzation and different techniques used to overcome the imbalance dataset, I divided the project into following stages:

•	Data preparation 
•	Train test split
•	Without using any sampling technique
•	Random under sampling
•	Oversampling Using Smote
•	Oversampling Using borderline Smote
•	Oversampling Using SVM Smote
•	Oversampling Using Adaptive Synthetic Sampling

Conclusion

Without using any sampling technique, I obtain a AP score of 0.84,F-1 score of 0.82 with knn and  voting classifier and bagging Classifier do provide improvement over knn but not significant improvement.
Under sampling and Oversampling techniques do help in improving recall but at expense of significant decrease in precision resulting in decrease in overall F-1 score. In addition, in case of oversampling with svm smote and borderline smote, we obtain a AP score of 0.86 with voting classifier but F-1 score much less than knn trained on dataset without using any sampling techniques.
Overall, Knn  trained on dataset without using any sampling techniques gave better results in all evaluation matrix


