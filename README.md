# suicide-attempt-prediction

---
layout: post
title:  "Suicide-Attempt-Prediction"
date:   2019-02-22
excerpt: "A project to predict suicide attempt based on data from reddit survey."
project: true
tag:
- python 
- colabnotebook
- suicide
- machinelearning
- unsupervised machine learning
comments: true
---

[CLICK HERE: Check out My Colab Notebook in Github Repo]()

![0](https://storage.googleapis.com/kaggle-datasets-images/1182/2125/cda8fa2e077f32a8d5fdeb78148d0261/dataset-original.jpg)    


      
## Overview
As the economy grows and the life quality improves, the happiness, however, doesn't increase accordingly.  According to estimates from the World Health Organisation (WHO), **over 800,000** people die due to suicide every year, which means that someone dies of suicide **every 40 seconds**. Nevertheless, the tragedy can be prevented if being intervened in time.

It's important to predict whether a person has the intention to suicide so that we can take actions if needed. The suicide involves many factors, both personal and societal one.
In this project, I used data from a survey created by a redditor in the subreddit *ForeverAlone* which collected demographic data and whether people attempted to suicide.

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


### EDA 
#### Numerical Variable
* Age Box Plot
![1](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/1.png)    

* Attrition Factors Heatmap
![2](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/2.png) 

* Take a look at the objective factors
![3](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/3.png) 

* Analysis on Monthly Income
![4](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/4.png) 
  Break the result by Job Involvement
![5](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/5.png) 

* Satisfaction
![6](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/6.png)


### Model
After several trials, I chose Logistic Regression

---

{% highlight yaml %}
from sklearn.model_selection import train_test_split

predictors = IBM_Attrition_Nu.drop(['Attrition'], axis=1)
target = IBM_Attrition_Nu["Attrition"]
x_train, x_val, y_train, y_val = train_test_split(predictors, target, test_size = 0.22, random_state = 0)

from sklearn.metrics import accuracy_score
from sklearn.linear_model import LogisticRegression

logreg = LogisticRegression()
logreg.fit(x_train, y_train)
y_pred = logreg.predict(x_val)
acc_logreg = round(accuracy_score(y_pred, y_val) * 100, 2)
print(acc_logreg)
>> 87.35
{% endhighlight %}

---

* Confusion Matrix
![7](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/7.png)

* Top 6 Influential Factors
![8](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/8.png)


## Conclusion
### Based on the influtial factors analysis
* Don't make them work overtime, they do care!
* Communicate the vision 
* Increase employee engagement, especially young employees
* Enhance recognition and rewards programs - Stock option can be a good choice 
* Create a pleasant workspace and increase satisfaction

### Since the model still need improvement in predicting attrition...
* Stay interview...
   e.g.
   “What kind of feedback or recognition would you like about your performance that you aren’t currently receiving?”

* Survey or interview with employees that decided to leave, identify the things employees care.
