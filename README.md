# Milwaukee Rampage FC
***
![milwaukee_rampage_fc.jpg](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/milwaukee_rampage_fc.jpg)
***
# Background

Milwaukee Rampage FC are a returning professional soccer club looking to form a professional women's team to enter into the second-tier of US Women's Soccer, the [United Women's Soccer (UWS)](https://uwssoccer.com/).

Milwaukee Rampage FC was founded in 1993 and formerly operated a men's professional team in the second-tier of US Soccer, first in the United States Interregional Soccer League (USISL), from 1994 to 1996, then in the A-League, from 1996 to 2002.

 Milwaukee Rampage FC feel the Milwaukee market is well positioned to support a second-tier team, with hopes of future expansion into the NWSL as the sport grows within the US.
* The [Chicago Red Stars](https://www.chicagoredstars.com/) have sustained a team in the US Women's first-tier, the [National Women's Soccer League (NWSL)](www.nwslsoccer.com), since 2013
* The [Milwaukee Wave](https://www.milwaukeewave.com/) are the longest continuously running professional soccer club in the US, playing in various iterations of the US Men's Indoor Soccer first-tier since 1984, including 6 national championships.

Milwaukee Rampage FC are in the process of building their support staff and infrastructure and have requested support from data science department.
***
# Business Problem

The Milwaukee Rampage FC have requested an expected goals model which can help predict the likelihood of goals based on available historical data, which the training staff can utilize to:
* Analyze game data and provide actionable recommendations for the training staff to help players  increase the likelihood of goals
* Assessing opponent teams and players and providing actionable recommendations for tactical planning
***
# Expected Goals (xG)

xG is a commonly referred to metric within soccer used to represent the probability a scoring opportunity may result in a goal.

xG is not a standardized metric, and therefore various data science companies, betting organizations, and teams build their own proprietary models to predict xG.
***
# Data

The data used has been sourced from [StatsBomb](https://statsbomb.com/), a United Kingdom based football (soccer) data analytics company.

StatsBomb have provided free access to their proprietary dataset via GitHub: [StatsBomb Open Data](https://github.com/statsbomb/open-data)
***
# Notebook Index

1. Data extracted in [expected_goals_data_extraction_notebook]()
2. Data organized in [expected_goals_data_organization_notebook]()
3. Features engineered in [expected_goals_feature_engineering_notebook]()
4. Data cleaned in [expected_goals_data_cleaning_notebook]()
5. Data explored in [expected_goals_data_exploration_notebook]()
6. Data preprocessed in [expected_goals_data_preprocessing_notebook]()
7. Model fitting and refinement in [expected_goals_model_fitting_notebook]()
8. Conclusions in [expected_goals_model_assessment_notebook]()
***
# Modeling

## Evaluation Metrics

The following metrics were used to assess the quality of the models tested (*in order of value*):
* **Recall** - Ratio of true positives, shots correctly identified as goals
* **ROC** - Area Under the Curve (AUC) for the Receiver Operating Characteristic (ROC); True Positive Rate (TPR) v False Positive Rate (FPR) plotted and the area under the curve of the plot measured
* **Accuracy** - Ratio of shots correctly identified
***
## Goal Ratio Baseline

10.91% of the total shots resulted in a goal.

This ratio was used as a baseline from which to assess other features.

![goals.png](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/goals.png)\
***
## Models

The following models were tested:
* Logistic Regression
* K Neighbors
* Decision Trees
* Random Forest
* Guassian Naive Bayes
* Support Vector Classifier
* Gradient Boosting
* XB Boost

The following ensemble methods were also tested:
* Bagging Classifier with Decision Trees
* Ada Boost with Decision Trees
* Ada Boost with Random Forest
* Voting Classifier with K Neighbors and Random Forest

# Results

## Random Forest Model

Random Forest performed best of all the models

![rf_report.PNG](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/rf_report.PNG)

![rf_roc.png](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/rf_roc.png)
***
## Feature Importance

![feature_importance.png](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/feature_importance.png)

### Shot Distance

![shot_distance.PNG](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/shot_distance.PNG)

![goals_shot_distance.png](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/goals_shot_distance.png)

**Conclusion**

Shots closer to goal have a higher likelihood of scoring

Shots closer to goal should be prioritized as a target in the team's player training and tactical planning
***
### Shot Angle

![shot_angle.PNG](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/shot_angle.PNG)

![goal_shot_angle.png](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/goal_shot_angle.png)

**Conclusion**

Shots from the left have a higher likelihood of scoring

Shots from this area should be prioritized as a target in the team's player training and tactical planning

**Conclusion**

Accounting for the importance of Shot Distance as well, passes to the left-side, inside of the 18-yard box should be prioritized as a target in the team's player training and tactical planning

## xG Applied to Data

* xG probability was predicted per shot and concatenated with the original dataset
* The difference between xG and actual goals was then calculated as xG_difference

### Filter by Player

![player_xG.PNG](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/player_xG.PNG)

Using these types of filters can help determine if a player is over or under scoring v their xG.

If a player is over-scoring, then the following hypothesis may apply:
* The player is an excellent finisher, capable of creating goals from lesser opportunities due to their outstanding personal ability
* The player is likely to experience a period of under-scoring as their trend reverts to the mean

(*The reverse hypothesis would be applicable to players under-scoring*)
***
### Filter by Team

![team_xg.PNG](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/team_xg.PNG)

Using these types of filters can help determine if a team is over or under scoring v their xG.

If a team is over-scoring, then the following hypothesis may apply:
* The team finishers are over-performing their creators resulting in a higher ratio of goals v quantity and/or quality of chances
* The team is likely to experience a period of under-scoring as their trend reverts to the mean

(*The reverse hypothesis would be applicable to teams under-scoring*)
***
### Next Steps

* Create a visual mapping shot location on a field diagram with a color-gradient for xG applied to shot points, visually indicating the distances and angles with the highest xG
* Engineer a feature creating a triangle of vectors from the shot location to each post of the goal, and then mapping if opposition players were between the shot and goal at the time of the shot
* Apply xG to match timestamp data, tracking accumulated xG throughout the match v the actual score and final outcome of the match
* Extract more assist-specific features in order to develop an Expected Assist (xA) metric
***
**Wes Swager**

[Email](mail.westin.swager@lsventures.com)

[LinkedIn](linkedin.com/in/wes-swager-36a84a2a)
