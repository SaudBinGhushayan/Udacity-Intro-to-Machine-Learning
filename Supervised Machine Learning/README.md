## Project Overview 
In this project I'm going to apply my knowledge in Supervised Machine Learning where I'm going to analayze and train the census data you can find it attached above as a csv file,

## Exploring the data
we have 13 features and only one outcome (target) which is the income of an individual ,
**Features**
- `age`: Age
- `workclass`: Working Class (Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked)
- `education_level`: Level of Education (Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool)
- `education-num`: Number of educational years completed
- `marital-status`: Marital status (Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse)
- `occupation`: Work Occupation (Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces)
- `relationship`: Relationship Status (Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried)
- `race`: Race (White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black)
- `sex`: Sex (Female, Male)
- `capital-gain`: Monetary Capital Gains
- `capital-loss`: Monetary Capital Losses
- `hours-per-week`: Average Hours Per Week Worked
- `native-country`: Native Country (United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc),
-  India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal,
-   Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand,
-    Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands)

**Target Variable**
- `income`: Income Class (<=50K, >50K)


## Preprocessing the data
I applied [Logarithmic Transformation](https://en.wikipedia.org/wiki/Data_transformation_(statistics)) so very high numbers and very low numbers don't affect the performance of the learning algorithm

after that I implemented a one-hot encoding for the categorical variables and then we end up with 103 features .

## Evaluating model performance 
I evaluated the data using a naive predictor as a base model the naive predictor is basically assumes that all individuals has income more than 50K which as it says `naive`. 

## Supervised models 
There are a varity of Supervised models but I chose only three to test their performance againt the student data

1- Logistic Regression : Since our goal is to predict individuals income if more than 50K or less than 50K and thats what logistic regression is used for so it will be a good candidate .

2- Adaboost Classifier : Since our dataset is large and it consists of more than 100 column it would be a good choice to choose Adaboost as a classifier model .

3- Random Forest Classifier: Since our dataset is complex and large Random Forest could be a great choice since it handles noisy and complex datasets .

Their performance was pretty good but Adaboost was the best with accuracy score of `0.86` and F-score of `0.72` 

![image](https://user-images.githubusercontent.com/82407781/133761586-fffe5dbd-1469-47da-93d6-ecf609c67ec7.png)


To view the results of each model :

![image](https://user-images.githubusercontent.com/82407781/133761678-3c18ee6d-0d2c-4de2-82a2-3bc293af3862.png)

## Optimizing the best model 

I optimized `Adaboost` model using the GridSearch with the base learner as a `Decision Tree Classifier`  with max_depth of 3

![image](https://user-images.githubusercontent.com/82407781/133761904-ce0c1c28-9096-44bf-880d-720827aa4e9a.png)


## Feature Relevance :

The most important features in our dataset is :

1- `education_num`

2- `hour_per_week`

3- `capital-gain`

4- `age`

5- `capital-loss`

![image](https://user-images.githubusercontent.com/82407781/133762119-fa75e36e-ece5-4bc1-9456-a55d07b14762.png)


## This project contain the following files : 

1- `census.csv` : the student data

2- `finding_donors.html` an HTML version of the notebook

3- `finding_donors.ipynb` the main file (notebook) which contains the code and implementation of the models 

4- `visuals.py` python code that displayes the metrics and performance of each model **NOTE** : I didn't write this code it was given to me with the project to assist me 



