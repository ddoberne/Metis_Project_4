# Metis Project 4: Live Win Probability in League of Legends
## Background
League of Legends (LoL) is a video game made by US-based Riot with an incredibly popular professional scene. Huya, a Chinese streaming platform, paid $310M for the exclusive broadcast rights for the next three years' worth of competitive LoL. In most major established sports, live win probability calculations have been established so that the win probability can be predicted from any scenario at any point in the game. In poker broadcasts, these probabilities are presented to the viewer. The goal of this project is to create a model that can predict, in live time, the win probability for a given team in a given situation. This will aid Riot in making their game attractive to viewers, as big plays will be able to be quantified in how much they can affect the predicted outcome of the game.

## Data
Data for this project will be taken from a LoL dataset from Kaggle with data from around 5000 matches, with each entry tracking the game progress as time goes on. The time of each event occurring will be critical to the model. The dataset has 57 features to pick from. Additional data can be acquired from various websites that track replay data.

## Algorithms
Logistic Regression and soft classification will be used to give the desired target. Success will be judged on the accuracy on the model, as sports are volatile and we are looking for a probability.

## Tools
SKLearn will be used for its Logistic Regression functionality. Seaborn and pandas will be used to help visualize and analyze the data. A dashboard will be created on Tableau to visualize the win probability as it changes over time for select exaples.

## Deliverables
The MVP will be a Logistic Regression model that predicts the probable outcomes at a select point in the game (15m). The final product will be able to give a prediction for any point in the game that should be in line with expectation from a viewer's standpoint.
