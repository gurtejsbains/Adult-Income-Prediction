# Adult Income Prediction 
## Using demographic factors to predict the income category in the dataset.  

**Author**: Gurtej Bains <br>
**Data Source**: [https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/ ](http://www.cs.toronto.edu/~delve/data/adult/adultDetail.html)

## Introduction:
The US Census Bureau collected this data in 1996. It captures the numerous variables that go into determining an individual's annual income. Education level, age, gender, profession, and education level are among the factors influencing income in this dataset. Using this dataset, let's examine the factors that influence salaries. Additional details about the dataset can be found here (http://www.cs.toronto.edu/~delve/data/adult/adultDetail.html)

## Executive Summary:
The model is unable to predict accurately the true annual salary (as a binary indicator). ML techniques were used to predict whether a person makes over $50K a year (class 1) or not. Several demographic factors were used to make this prediction.
In addition to Random Forest, a KNN classification model was fitted. In addition to selecting features, Grid Search was used to determine the most suitable parameters. There are two categories of annual salaries in this dataset: those under $50K and those over $50K. Below are additional callouts:
1.	There are 48,842 observations in the dataset with 15 features.
2.	There are 76% of the data with salaries below $50K.
3.	The salaries of people with higher education tend to be higher.
4.	A typical week for a person is between 30 and 40 hours.
5.	There are some discrepancies in the data. An example would be the capital gain of $9999, which doesn't follow any pattern.
6.	The private sector employs the majority of workers.
7.	The United States is the native country of approximately 90% of the observations. 
8.	Duplicate information is represented by education-num and education.

<p align = "center"> 
  <img src = "https://github.com/gurtejsbains/Adult-Income-Prediction/blob/5af82ae3235cd092e051dec059642e0dc654cc4e/Age%20and%20hours%20worked%20per%20week.png">
</p>

<p align = "center"> 
  <img src = "https://github.com/gurtejsbains/Adult-Income-Prediction/blob/3c7d922c818a0a259289b35c46740662833e2881/Age%20and%20net%20capital%20gains.png">
</p>

## Data Dictionary: 
1.	workclass: Identifies the work/job.
2.	education: Identifies the highest education level.  
3.	education-num: Identifies the highest education level as a number.
4.	marital-status: Identifies the marital status.
5.	occupation: Identifies the occupation.
6.	relationship: Identifies the relationships like wife or husband, etc.
7.	race: Identifies the race of the person.
8.	sex: Identifies the gender.
9.	native country: Identifies the native country of the person.
10.	age: Identifies the age of the person.
11.	fnlwgt: final weight. Calculated by US the Census Bureau.
12.	capital-gain: Identifies capital gains.
13.	capital-loss: Identifies capital loss.
14.	hours-per-week: Identifies total hours worked per week.
15.	Income: Binary target. Identifies the income.
 
## Model Interpretation and Recomendations:
1.	Out of all the models, Grid Search tuned Random Forest without PCA wins.
2.	As part of this analysis, “Accuracy Score” is considered to be the key measurement indicator. Due to the importance of accurately identifying salaries in the business.
3.	Both the basic and tuned Random Forest model had the same Accuracy Score. A higher AUC Score was used as a tie breaker. Tuned Random Forest has the highest AUC Score hence the winning model.
4.	An Accuracy Score of 85% and AUC Score of 91% was achieved by the winning model.
5.	In terms of model predictive accuracy, PCA shows no material improvement.
6.	While model accuracy may appear strong, other key indicators like True Positive rate and Recall were weak.
7.	Model was run on a powerful personal laptop using JupyterLab. The entire code is executed in approximately 5 hours (299 minutes). 
8.	This model in the current state is not suitable for production. Below mentioned recommendations should be tested and model to be refit to determine if performance can be improved. 

## Technical next steps: 
1.	Some features will require additional engineering work. For example, education can be classified as 'doctoral', 'master', 'bachelor', or ‘high school or less’. This will reduce the cardinality. This feature currently has 17 values. A similar binning can be applied to marital status features.
2.	Outlier treatment: Outliers are identified in the hours-per-week feature.
3.	Capital gains and losses can be used to calculate the capital delta. 
