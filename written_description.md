# Win Probability in League of Legends
## Design
League of Legends (LoL) is a video game made by US-based Riot with an incredibly popular professional scene. Huya, a Chinese streaming platform, paid $310M for the exclusive broadcast rights for the next three years' worth of competitive LoL. In most major established sports, live win probability calculations have been established so that the win probability can be predicted from any scenario at any point in the game. The goal of this project is to create a model that can predict, in live time, the win probability for a given team in a given situation. This will aid Riot in making their game attractive to viewers, as big plays will be able to be quantified in how much they can affect the predicted outcome of the game.

An example win probability chart of a match between TSM and CLG created by this project can be viewed here: https://public.tableau.com/app/profile/dayv.doberne/viz/TSMvs_CLG2016NACLSSpringPlayoffs/Dashboard1?publish=yes
## Data
Data was taken from 7.6K professional matches played from 2015-2017 from [Kaggle](https://www.kaggle.com/chuckephron/leagueoflegends). 24 features were used in training of the model. Each event recorded in the features was timestamped, which was taken into consideration for training of the model.

The Target for this project was bResult; whether Blue won or lost the game. Features used were game length, blue kills, blue towers, blue inhibitors, blue dragons, blue Barons, blue heralds, red kills, red towers, red inhibitors, red dragons, red Barons, red heralds, overall gold differential, blue top gold, blue jungle gold, blue mid gold, blue ADC gold, blue support gold, red top gold, red jungle gold, red mid gold, red ADC gold, and red support gold.
## Algorithms
Logistic regression and random forest models were compared for this project, with the regression scoring higher in accuracy. Accuracy was chosen as the metric of choice because the impact of red or blue winning was virtually the same; there weren't repurcussions for false negatives or false positives. Accuracy for this model ranged from 0.62 to 0.85 depending on time, which is satisfactory given the variance in predicting sports outcomes. The regression model was cross-validated with a K-fold of 5.

One of the big challenges of this project was feature engineering to account for time elapsed, especially since the total time of a League of Legends game is not predetermined. The model was trained and predictions were made to only include events that had already happened before the minute that was being predicted for. Further feature engineering was done to increase interpretability of the regression model, using standardized gold differential per role rather than having separate values for both teams.
## Tools
* LogisticRegression and RandomForest from sklearn
* pandas and Google Sheets for managing data
* Tableau and seaborn for data visualization
## Communication
* Tableau dashboard from above
* [Presentation Slides](league_of_legends_win_probability.pdf)
* Blog post, but only once I'm settled after moving to Seattle
## Future improvements
* More data, and more recent data
* Using some model overlap to prevent overfitting. Occasionally there would be an unexplained jump in the win probability of a match, where the value would go from .9+ to .1- back up to .8+ within the span of a few minutes. Figuring out why this happens and how to make sure the model doesn't change too widely from minute to minute would help in predictions of longer games
* League of Legends API so that a player could plug their own replay data into a program, which could then produce a win probability chart like above
