# Suicide Attempt Prediction

[CLICK HERE: Check out My Colab Notebook in Github Repo](https://github.com/lanzizuan/suicide-attempt-prediction/blob/master/Suicide_Attempt_Prediction.ipynb)

 


      
## Overview
---
As the economy grows and the life quality improves, the happiness, however, doesn't increase accordingly.  According to estimates from the World Health Organisation (WHO), **over 800,000** people die due to suicide every year, which means that someone dies of suicide **every 40 seconds**. Nevertheless, the tragedy can be prevented if being intervened in time.

It's important to predict whether a person has the intention to suicide so that we can take actions if needed. The suicide involves many factors, both personal and societal one.
In this project, I used data from a survey in a subreddit called *ForeverAlone*(https://www.reddit.com/r/ForeverAlone/) which collected demographic data and whether people attempted to suicide.

![1](https://ourworldindata.org/wp-content/uploads/2016/06/GenderAge-768x481.png)

Source: (José Manoel Bertolote and Alexandra Fleischmann, Suicide and psychiatric diagnosis: a worldwide perspective. World Psychiatry 1:3, October 2002.

#### Survey question
1.  What is your Gender?	
2. What is your sexual orientation?	
3. How old are you?	
4. What is your level of income?	
5. What is your race?	
6. How would you describe your body/weight?	
7. Are you a virgin?	
8. Is prostitution legal where you live?	
9. Would you pay for sex?	
10. How many friends do you have in real life?
11. Do you have social anxiety/phobia?	
12. Are you depressed?	
13. What kind of help do you want from others? (Choose all that apply)	
14. Have you attempted suicide?	
15. Employment Status: Are you currently…?	
16. What is your job title?	
17. What is your level of education?	
18. What have you done to try and improve yourself? (Check all that apply)	



## Process  
---
### EDA 
#### Numerical Variable

* What's the distribution of age?

![2](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/1.png)    

* How many friends in real life?

![3](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/2.png) 

#### Categorical Variable

* Relationship between educational level and suicide attempt

![4](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/3.png) 

* Relationship between body weight and suicide attempt

![5](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/4.png) 

* Relationship between income and suicide attempt

![6](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/5.png) 

#### Word cloud

* For people who have attepmted to suicide, what kind of help do they need?

![7](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/6.png)

* What's the job of people who have attempted to suicide?

![8](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/7.png)



### Technique for pre-modeling task
---
 
1. SMOTE (Synthetic Minority Oversampling Technique): oversampling. deal with the imbalance of suicide and not suicide.
2. RFE(Recursive Feature Elimination): Test out the features which can give the best model performance.



### Modeling
---

I used Logistic regression, KNN classifier, Random Forest and did grid search CV on the latter two. 


* Model Performance

![9](https://raw.githubusercontent.com/lanzizuan/suicide-attempt-prediction/master/image/8.png)



### Conclusion
---
#### About Suicide
 
 Based on the survey, six features have influence on one's intention to suicide:
 * depressed (2.8929) 
 * sexuallity_Straight (-2.0080) 
 * gender_Male （-1.0198）
 * body weight (0.5365) 
 * edu_level (-0.3293) 
 * income (0.1933)

#### About Modeling

During the process of feature selection and model selection, it's not necessary to find the best one, but a good enough one.
* The RFE visualizer show that a logistic regression model with 5 features will be the best accurate one. Considering the complexity of suicide, some important information might lose if I only keep 5 features.

#### Next step

* Try out different ways to encode categorical variables. (gender_male has negative coefficient obeys the common sense.)
* Used the important features gotten from this analysis to analyze people's post on twitter or reddit to find out people who tend to suicide and make some intervention.
