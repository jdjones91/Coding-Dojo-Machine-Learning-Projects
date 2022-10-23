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

The reason behind this is simple: this generates the most balanced predictions. This model predicted some stage 2, 3, and 4 cirrhosis cases, but did not correctly predict stage 1. The other model, however, did not correctly predict stage 1 or 2. Therefore, the Logistic Regression model seems to have learned the difference between stages most effectively. This is largely due to class imbalance in our target (Stage), which can be visulized with a histogram.

<img width="382" alt="Histogram of Stage (of Cirrhosis)" src="https://user-images.githubusercontent.com/109368648/197408388-7990a27f-3cde-4ead-a3ab-13df606fe703.png">

  - Prediction of later stages (more severe illness) was most likely more successful because the feature values were more extreme. In addition, our model had more stage 3 and stage 4 targets to learn about. 
 
This model, currently, could be put into practice only as a way to increase the amount of data fed into the model, and to increase it's reliability over time. This should not be relied on to make clinical predictions.
 - This model's performance can be improved by gathering more data, and adding more highly correlated data points (chemical blood concentrations, co-morbidities, etc), with the help of a subject matter expert.
- This model, to be truly successful, needs more information correlated to stage 1 and stage 2 cirrhosis. As is the case with all medical condition, the earlier the diagnosis, the better.

