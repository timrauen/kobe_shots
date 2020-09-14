# kobe_shots
Kobe Bryant Made Basket Predictor

Problem: How can I predict whether or not Kobe Bryant will make a given basket? 

Data collection:
I downloaded the dataset from https://www.kaggle.com/c/kobe-bryant-shot-selection. As can be expected with many kaggle competitions, the data had no null values that needed to be accounted for.

EDA:
Over Kobe's career he made about 44.6% of his shot attempts. Dunks were his highest percentage shot at around 93% while tip shots were the lowest at around 35%. Kobe's shot percentage was highest in the first quarter (46%) and lowest in the fourth quarter (41%), which can be attributed to fatiuge over the course of a game. Despite his reputation for being clutch at the end of a game he shot under 40% in the last two minutes of a game. His home shooting percentage was about 2% higher than on the road. There was virtually no difference between his shooting in the regular season vs. the playoffs.
Overall, no one statistic was strongly correlated with whether or not the shot was made. The most strongly correlated features are shot distance, shot type (dunk vs jump shot made a big difference) and whether or not he was driving on the shot. These featues are exhibited acorrelation of 0.2. 

Models:
I tried a number of different models. The ones with the best accuracy were logistic regression with l1 regualrization (.630), random forest classifier (.624), adaboost classifier (.629). A voting classifier of all of my models produced an accuracy of .629. My confusion matrix looked like this:

Predicted               missed       made

Actual missed          [3397,        161],
Actual made            [2221,        646]

Interestingly, this model has very high precision. It rarely predicts that Kobe will make his shots. 
