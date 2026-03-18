## March Machine Learning Mania ##
In this notebook contestants are tasked with analysing data to create predictions for the NCAA March Madness Tournament. These predictions involve every matchup possible out of the teams eligible for the competition, this leads to the creation of 132,133 predictions being made.

Over 30 csv files are available to use for model training but the most important part of creating a model that will have a higher chance of prediction correctly is the feature engineering.

My model was influenced by the 2019 winning submission Raddar's notebook. I introduced new statistics into the dataset using the available data to try and increase the model training capabilities. Some of the key features I introduced were;
- ELO Ranking and MOV-ELO Ranking (Margin-of-Victory ELO): This ranking systems provides teams with a score based on how they have played, the Margin of Victory ELO ranking was designed to display teams that were constantly winning or losing with large margins be either heavily penalised or heavily rewarded.
- SOS (Strength of Schedule): This feature was designed to track a teams opponents ELO to show how strong the opponents they have played have been.
Momentum - This feature keeps track of teams last 10 games, this is aimed to describe a team being "in-form" or "out-of-form" in the leadup to the tournament. A team that started the season winning 26 games and losing their last 8 should not be recognised as the same as a team that has finished the season on a 26 game win streak.

When training my model I did not just stick with one model. I used a Tabular-Foundation Model (TabICLv2) as a classifer to try and predict just wins and losses, which was ensembled with a XGBoost and LightGBM model that was predicting point differential. By seperating these into two different predictors the aim was to releive some stress from the models so that accuracy could be improved.

I am impressed with how the model has trained, the tournament is not yet finished so I am unsure of how the model will score, however running against the data from tournament in 2025, my submission would have been a top300 submission in the competition
