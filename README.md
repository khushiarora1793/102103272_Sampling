# TITLE : Exploring Machine Learning Techniques- Sampling Methods and Model Evaluation
By Khushi Arora 102103272 B.E Computer Engineering ,TIET Patiala

# 1. Methodology
![image](https://private-user-images.githubusercontent.com/90442567/301607718-98071500-447b-4fc5-bcd4-130d346303b0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDY5NDc5NjUsIm5iZiI6MTcwNjk0NzY2NSwicGF0aCI6Ii85MDQ0MjU2Ny8zMDE2MDc3MTgtOTgwNzE1MDAtNDQ3Yi00ZmM1LWJjZDQtMTMwZDM0NjMwM2IwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAyMDMlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMjAzVDA4MDc0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQ2MTlkMzgwNWRhOGQzNzhiODdlMDQ2OTM4ZmE2MDdkOGQxNzVmMWFiNTFhMTE0ZjdiZjBiMGExMWVhZWJlMzQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.erJcs1UZ9Dl7cxJJIaVbiPF8CxgIQngELDyzRRHudf8)
# 2. Description
## Stage 1 :
In this Assignment, We were given a Credit Card Dataset comprising of 772 instances and 31 features, out of whixh on checking it was found that the data had 763 instance of Class 0 and only 9 instances of Class 1, pointing to the fact that the dataset is highly imbalanced.

Following Pie-Chart Shows the Class Imbalance :

![image](https://github.com/khushiarora1793/102103272_Sampling/blob/main/102103272_piechart.png)

## Stage 2:
In Order to balance the dataset, I used RandomOverSampler, it's an effective technique for dealing with imbalanced datasets. RandomOverSampler randomly duplicates instances from the minority class until it is balanced with the majority class. This method is simpler compared to SMOTE, as it doesn't involve creating synthetic samples but instead replicates existing minority class instances.

## Stage 3:
After Balancing the Dataset, we obtained equal number of instances for both the Classes(0 & 1).
Following are the briefings about the balanced Dataset :

Class Distribution of Balanced Dataset:
0    763
1    763
Name: Class, dtype: int64

Following Bar-Chart Shows the Class Distribution after Balancing the Dataset :
![image](https://github.com/khushiarora1793/102103272_Sampling/blob/main/102103272_bar.png)

Now 5 different Sampling Techniques were applied on the Balanced Dataset ,which are mentioned as below :

(i) Simple Random Sampling:
Randomly selects a specified number of samples from the dataset without any specific criteria.

(ii)Stratified Sampling:
Divides the dataset into strata or groups based on a specific feature (e.g., class labels).

(iii)Cluster Sampling:
Divides the dataset into clusters or groups.
Randomly selects entire clusters and includes all samples within those clusters in the sample.

(iv)Bootstrap Sampling:
Creates multiple samples by randomly resampling with replacement from the original dataset.
Useful for estimating the distribution of a statistic or creating multiple datasets for model training.

(v)Systematic Sampling:
Selects samples at regular intervals after an initial random start.
Requires defining a sampling interval, and it's less prone to bias than simple random sampling.

## Sample size calculation

For Simple Random Sampling :
The sample size is calculated as: n=Z^2*p*(1-p)/E^2
where n=sample size, p=standard deviation , Z= z-score , E= margin of error

For Stratified Sampling :
The sample size is calculated as: n=(Z^2 * p * (1 - p)) / (E/S)^2)
where n=sample size, p=standard deviation , Z= z-score , E= margin of error ,S= number of strata

For Cluster Sampling:
The sample size is calculated as: n=(Z^2 * p * (1 - p)) / (E / C)^2)
where n=sample size, p=standard deviation , Z= z-score , E= margin of error, C is avg size of cluster

## Stage 4:

After applying the Sampling techniques on the Balanced Dataset, each of the samples were splitted into train and test data and fed into 5 different models and an Accuracy Score was obtained.

Following are the Models that were used :

(i)Logistic Regression:
A binary classification algorithm that models the probability of a binary outcome.
It's interpretable and provides coefficients for each feature, indicating their impact on the outcome.

(ii)Decision Tree:
A tree-like model where each node represents a feature, each branch a decision, and each leaf an outcome.
It's capable of handling both classification and regression tasks and is interpretable.

(iii)Random Forest:
An ensemble learning method that constructs multiple decision trees during training and outputs the mode of the classes (classification) or the mean prediction (regression) of the individual trees.
Combines the strength of multiple trees to improve overall accuracy and generalization.

(iv)Support Vector Machine (SVM):
A powerful classification algorithm that finds the hyperplane that best separates classes in a high-dimensional space.
Effective for both linear and non-linear classification tasks and works well in high-dimensional spaces.

(v)K-Nearest Neighbors (KNN):

A lazy learning algorithm that classifies a data point based on the majority class of its k-nearest neighbors.
The choice of 'k' and the distance metric are critical parameters in KNN.

These models were applied to various samples obtained through different sampling techniques to understand their performance and how they generalize to different subsets of the dataset. 

# 3.Input/Output
Input: Credit Card Dataset which can be downloaded from my repository too.
Output: Accuracy Score of Various Models on 5 different Samples.

Following Table summarises Our Final Outcome in form of accuracy values obtained for different Models after applying them on samples obtained through various Sampling Techniques :

![image]
# 4.Result :
Decision Tree Obtained the Highest Accuracy Score on Bootstrap Sample among the samples and also performed really well on the five samples in comparison to the other models that we used for our analysis.
