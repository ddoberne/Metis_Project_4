# MVP
## Background
League of Legends (LoL) is a video game made by US-based Riot with an incredibly popular professional scene. Huya, a Chinese streaming platform, paid $310M for the exclusive broadcast rights for the next three years' worth of competitive LoL. In most major established sports, live win probability calculations have been established so that the win probability can be predicted from any scenario at any point in the game. In poker broadcasts, these probabilities are presented to the viewer. The goal of this project is to create a model that can predict, in live time, the win probability for a given team in a given situation. This will aid Riot in making their game attractive to viewers, as big plays will be able to be quantified in how much they can affect the predicted outcome of the game.
## Model
Using match data from 7620 matches, a logistic regression model was built to predict the outcome of a game given data at the 15 minute mark. The model was able to predict the winner with 75% accuracy based on gold differential; change in gold differential over the last 1, 3, and 5 minutes; kill differential; tower differential; inhibitor differential; dragon differential; and herald differential. The following coefficients show the relative strengths of each feature:
~~~
golddiff15 coef: 1.74
golddiff-1 coef: 0.07
golddiff-3 coef: -0.12
golddiff-5 coef: 0.24
killdiff coef: -0.12
towerdiff coef: -0.45
inhibdiff coef: -0.01
dragdiff coef: 0.36
heralddiff coef: -0.01
~~~
Given the inherent unpredictable nature of sports, this accuracy is promising, but I am hoping to improve upon it with feature engineering and cross-validation. Looking at the recency of events to detect momentum will also be something to fit in. Once I am satisfied with the 15-minute mark, I will use a similar approach to build a model for each part of the game so the win probability can be calculated throughout.

![histogram](/Histogram.png)

Accuracy of the current model

![confusion](/Confusion.png)

Confusion matrix, with true positives in the bottom right and false negatives in the top left.

![ROC](/ROC.png)

ROC curve for the current model
