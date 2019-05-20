# Suicide Attempt Prediction
This repository contains the entire analysis and predictive modeling of suicide, in the form of Colab notebooks.

[CLICK HERE: Check out the Colab Notebook in Github Repo](https://github.com/lanzizuan/suicide-attempt-prediction/blob/master/Suicide_Attempt_Prediction.ipynb)

 


      
## Overview
---
As the economy grows and the life quality improves, the happiness, however, doesn't increase accordingly.  According to estimates from the World Health Organisation (WHO), **over 800,000** people die due to suicide every year, which means that someone dies of suicide **every 40 seconds**. Nevertheless, the tragedy can be prevented if being intervened in time.

It's important to predict whether a person has the intention to suicide so that we can take actions if needed. The suicide involves many factors, both personal and societal one.
In this project, I used data from a survey in a subreddit called *ForeverAlone*(https://www.reddit.com/r/ForeverAlone/) which collected demographic data and whether people attempted to suicide.

The objective of this project is to **understand the attributes of people who attempted to suicide** and use it as reference to infer whether a person will try to suicide or not.

![1](https://ourworldindata.org/wp-content/uploads/2016/06/GenderAge-768x481.png)

Source: (José Manoel Bertolote and Alexandra Fleischmann, Suicide and psychiatric diagnosis: a worldwide perspective. World Psychiatry 1:3, October 2002.



## Table of Content

1. Ingest

 * 1.1 Import Packages

 * 1.2 Import Dataset
 
 * 1.3 Data Cleaning
 
 * 1.4 Feature Encoding

2. Exploratory Data Analysis

3. Modeling

 * 3.1 Pre-modeling task
 
   * 3.1.1 Split training/test set
   
   * 3.1.2 Over-Sampling Using SMOTE(Synthetic Minority Oversampling Technique)
   
   * 3.1.3 Feature Selection Using Recursive Feature Elimination (RFE)
 
 * 3.2 Logistic Regression
 
 * 3.3 KNN Classifier
 
 * 3.4 Random Forest

4. Conclusion
 

 
 

## Visualization Excerpt 
---

#### Word Cloud

* For people who have attepmted to suicide, what kind of help do they need?

![4](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/6.png)

Observation: When people ask for dating with others, they might feel lonely and the risk of attempting to suicide arises.


* What's the job of people who have attempted to suicide?

![5](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/7.png)

Observation: Student/engineer/unemployed people are most likely to suicide, probably because they have more stress than others.



#### Heatmap


![6](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/7.png)

 Based on the heatmap, six features have most influence on one's intention to suicide:
 * depressed (2.8929) 
 * sexuallity_Straight (-2.0080) 
 * gender_Male （-1.0198）
 * body weight (0.5365) 
 * edu_level (-0.3293) 
 * income (0.1933)
 
 Suggestion: When people around you express their depress, you should take care of them because they might face some difficulties and might attempt to suicide while the situation worsens. If your friend is not straight, he/she has higher probability to attempt to suicide than others. Besides, female/over-weight/low educational/high income people are more likely to suicide as well.
 
## Technique Used for Pre-modeling Task
---
 
1. SMOTE (Synthetic Minority Oversampling Technique): Oversampling, deal with the imbalance of classes: attempted to suicide and not attempted to suicide.
2. RFE(Recursive Feature Elimination): Test and return the best combination of feature of a certain number.


