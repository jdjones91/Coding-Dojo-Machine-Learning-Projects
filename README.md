# Coding-Dojo-Machine-Learning-Projects

## For this project I took a Liver Cirrhosis dataset from Kaggle (link in project) and built several ML models to see if the information given, could be used to predict the stage(stage 1, stage 2, stage 3, stage 4) of patient Cirrhosis, and ultimately put into production.
  - About half of the work found in 'Project 2, Final' is related to data cleaning and explorations, and the other half dedicated to building, tuning, and comparing ML models. *This project contains a lot of commentary and some extra pieces of code for demonstration purposes.*

What I found was that of the information recorded, there was very little actual correlation to our target ('Stage' of cirrhosis). Despite this, I executed and tuned 3 separate classification models, then applied PCA to the best 2 (which, after tuning, actually had identical accuracy scores on the testing set).

<img width="1100" alt="Screen Shot 2022-10-20 at 12 44 09 PM" src="https://user-images.githubusercontent.com/109368648/197031893-429f51c3-ce5e-4cd5-8bbd-815330e12f35.png">

- Heatmap showing correlation of numerical data

My best model (and fastest; executing in milliseconds), was a tuned Logistic Regression model with the addition of PCA. This model, however, still only had an accuracy score of 0.53 (full classification report inside project notebook). The model can be summarized below:

- Final model to put into production: Logistical Regression:
  - Hyperparameters: C = 1, solver = 'saga', penalty = 'l1', random_state = 42, max_iter = 10000
    - With the addition of PCA(n_components = 16)

## The reason behind this is simple: this generates the most balanced predictions.
## While the Logistic Regression model is still poor, it has the most balance in predictions, and is incredibly quick. 
# This model could be put into practice only as a way to increase the amount of data fed into the model, and to increase it's reliability over time. This should NOT be relied on to make clinical predictions.
### This models performance can be improved by gathering more data, and adding more highly correlated data points (chemical blood concentrations, co-morbidities, etc), with the help of a subject matter expert.
- ## This model, to be truly successful, needs more information correlated to stage 1 and stage 2 cirrhosis. As is the case with all medical condition, the earlier the diagnosis, the better.

