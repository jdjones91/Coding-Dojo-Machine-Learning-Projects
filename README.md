# Coding-Dojo-Machine-Learning-Projects
### *This is my second project while attending Coding Dojo. All work is cumulative, and the final version can be seen in full under "Project 2 Part 4"*

## For this project I took a Liver Cirrhosis dataset from Kaggle (link in project) and built several ML models to see if the information given, could be used to predict the stage(stage 1, stage 2, stage 3, stage 4) of patient Cirrhosis.
  - ### In "Project 2 Part 4" you will find that about half of the work is related to data cleaning and explorations, and the other half dedicated to building, tuning, and comparing ML models. *This project contains a lot of commentary and some extra pieces of code for demonstration purposes.*

What I found was that of the information recorded, there was very little actual correlation to our target ('Stage' of cirrhosis). Despite this, I executed and tuned 3 separate classification models, then applied PCA to the best 2 (which, after tuning, actually had identical accuracy scores on the testing set).

<img width="1100" alt="Screen Shot 2022-10-20 at 12 44 09 PM" src="https://user-images.githubusercontent.com/109368648/197031893-429f51c3-ce5e-4cd5-8bbd-815330e12f35.png">

- Heatmap showing correlation of numerical data

## My best model (and fastest; executing in milliseconds), was a tuned Logistic Regression model with the addition of PCA. 

