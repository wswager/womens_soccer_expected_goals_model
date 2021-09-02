# What is xG?

_The metric changing the way soccer is interpreted_
***
![soccer_field_background.jpg](https://github.com/wswager/milwaukee_rampage_fc/blob/main/images/soccer_field_background.jpg)
***
# Introduction

In the following blog post I discuss the [expected goals](https://en.wikipedia.org/wiki/Expected_goals) (xG) metric for soccer, its origins, how it works, and why it has become so important in the way the game is analyzed.

Full disclosure, the [Data Science Bootcamp](https://flatironschool.com/campus-and-online-data-science-bootcamp/) I enrolled with[ Flatiron School](https://flatironschool.com/welcome-to-flatiron-school/?utm_source=Google&utm_medium=ppc&utm_campaign=12728169839&utm_content=127574231184&utm_term=flatiron%20school&uqaid=513799628798&CjwKCAjwiLGGBhAqEiwAgq3q_nzPYrEWzpEpuwBOgdki5zv1VCYeHFflfmTr8NnOLN-Tp9DoyNntwxoCnj0QAvD_BwE&gclid=CjwKCAjwiLGGBhAqEiwAgq3q_nzPYrEWzpEpuwBOgdki5zv1VCYeHFflfmTr8NnOLN-Tp9DoyNntwxoCnj0QAvD_BwE) requires four blog post submissions as part of the curriculum.  This is the forth of my posts, for phase four.


## Index



*   History
*   Definition
*   Misconceptions
*   How is xG Calculated?
*   How is xG Applied?
*   Future of xG
***
# History

_‘Quality without results is pointless, results without quality is boring’_

_Johan Cruyff_

 In 2002, ‘[moneyball](https://en.wikipedia.org/wiki/Moneyball)’ transformed baseball, when the Oakland Athletics utilized ‘[sabermetrics](https://en.wikipedia.org/wiki/Sabermetrics)’ models to overperform what their budget suggested they were capable of through the use of advanced data science.  

In much the same way, data science has begun to penetrate the highest levels of soccer, largely exemplified by the popularization (and its subsequent polarization) of the xG metric.

In 2004, Jake Ensum, Richard Pollard and Samuel Taylor conducted a study of matches from the 2002 World Cup ‘to investigate and quantify factors that might affect the success of a shot,’ and using logistic regression identified five factors that had a significant effect:



*   Distance from Goal
*   Angle from Goal
*   Distance from Nearest the Defender
*   If the Assist was a Cross
*   Number of Players Between the Shot and Goal

In 2012, Sam Green, of [Opta](https://www.optasports.com/), a British sports analytics company, introduced the term  'expected goals' and ‘xG’ in regards to football (soccer).  He described the metric calculated by Opta as a means to:



*   ‘Accurately and effectively increase our chances of scoring and therefore winning matches’
*   ‘Use data from a defensive perspective to limit the better chances by defending key areas of the pitch’
*   ‘Look at each player's shots and tally up the probability of each of them being a goal to give an expected goal (xG) value’

Early adoption by betting markets has since helped xG become a regular feature of mainstream soccer broadcasts and media analysis.
***
# Definition

_‘The most difficult thing in [soccer] is to score a goal’_

_Pep Guardiola_

xG is a measurement of the quality of a shot.

xG calculates the likelihood that a shot will be scored based on a combination of features regarding the shot itself and the play leading to the shot.

xG is measured on a scale between zero and one, with zero representing no goal and one representing a goal.
***
# Misconceptions

_‘[xG] must be the most useless stat in the history of football! What does it tell you? The game’s finished 3-1, why do you show expected goals afterwards?’_

_Jeff Stelling, Sky Sports Soccer Analyst_

Criticisms of xG often cite scenarios where the metric differs from the actual outcome.  If a  game ends 1-0, but the expected goals isreversed, 0.57-1.13, critics will often claim that the metric is flawed.  However, xG is only intended as a measurement of chance quality and not as a predictor of the eventual outcome of the game.  Variance is expected, but long-term is expected to regress toward the mean.  

Also,  xG, as with all calculated metrics, should be refined and adjusted over time for accuracy, so a long-term trending difference can actually help in making those appropriate refinements and adjustments to improve the quality of the metric.

Another misconception is in the literal interpretation of the name, ‘expected goals.’  xG is not a literal ‘expectation’ of if goals will be scored (see above, xG is not a predictor of the outcome).  The name ‘expected goals’ is derived from the mathematical concept ‘expected value,’ a measure of the likelihood of an outcome occurring.  For example, the expected value of a fair coin toss landing on heads is 50%.

Another note on variance, a player or team over or underperforming their xG, does not impact future predictions.  This is the concept of ‘[Gambler’s Fallacy](https://en.wikipedia.org/wiki/Gambler%27s_fallacy)’, which dictates that the outcome of previous examples does not affect the likelihood of future outcomes.  For example, given a large sample, the expectation is the average across all coin tosses will average 50%, however, a coin landing heads three-times in a row does not change the likelihood of the next coin toss being heads is still 50%.
***
# How is xG Calculated?

_You study and think and discuss, and you come up with a model of playing._

_Carlo Ancelloti_

xG is not a standardized metric, and, therefore, many different proprietary variants exist amongst various sports analytics organizations, betting companies, soccer clubs, etc.

That said, generally, xG is built using a classifier model with input from a large historical dataset of shots, incorporating a number of variables which have been deemed to significantly affect the likelihood of a goal being scored. 

Some of the most commonly incorporated variables in current top performing models are:



*   Distance to the Goal
*   Angle to the Goal​
*   Opponent Players Between the Shot and Goal
*   Total Players Between the Shot and Goal
*   Bodypart Used to Shoot
*   Type of Assist
*   Pattern of Play

The variables are then used to fit the classification model and produce a prediction percentage for each shot, which is labeled the xG.
***
# How is xG Applied?

_‘[Soccer] is like hunting. One second can change it all, but it's not just any second, it's a flash. The prey is there and suddenly then it's not. In an instant it's over - you won't have the chance again. You need to know which one precise second to train for, and to understand that moment.’_

_Diego Simeone_

By quantifying the quality of shots, xG, adds context beyond traditional statistics, by assigning a measure to the quality of shots.  

The most direct application of xG is to assess an individual shot for its quality, either to assess if a miss was a ‘good’ shot or to assess how difficult a goal was to score.  For training, assessing individual shots can provide actionable recommendations using correlations between significant variables and xG v the values of those features in the shot being analyzed.  For example, if a shot was taken 20-yards from goal, but there was an opportunity to take an additional dribble and shoot from 15-yards, then a comparison between the xG of the actual shot and the xG of a shot with the same features but the improved distance from goal can help quantify the difference in quality.

Another application of xG is measuring cumulative xG.  The cumulative xG of a player across the course of a game or set of games (for example, across an entire season) can be used in comparison with actual goals to assess over or underperformance.  For example, a player underperforming their xG across a season may require additional technical training to help improve their finishing.  Cumulative xG for a player can also be used in comparison to other players to assess quality of shots v actual goals.  For example, two players who scored a similar number of goals from a similar number of shots can then be compared by the quality of their shots, with smaller difference in xG v actual goals indicating a player who is more likely to maintain their current rate of scoring.

Similarly to cumulative xG for players cumulative xG can also be measured for a team, with similar types of assessments.  This is often one of the main applications of xG for betting purposes.  For example, a team winning games but significantly overperforming their xG might be expected to have a slump in form on the horizon if they regress toward the mean of their xG.

Another accumulation metric for xG is xG based on timestamps across the course of a match.  This type of measurement would demonstrate the accumulation of xG with each shot taken throughout a match and can be compared v the actual goals and the eventual outcome.  This can help indicate the state of the game over time.  If a team is creating a high quantity of high quality shots over a period of time, this can suggest they have been successful in an attacking sense toward threatening the opposition goal.  The reverse may also be true, if a team is not creating a high quantity of high quality chances, this can suggest the defensive team’s efforts have been successful.

Because soccer is a relatively low scoring sport, the ability to measure the likelihood of a goal being scored can be  essential context toward quantifying the flow and story of a match or a series of matches. 
***
# Future of Data Science in Soccer

_‘I tell the players that the bus is moving. This club has to progress. And the bus wouldn't wait for them. I tell them to get on board.’_

_Sir Alex Ferguson_

While xG may be the most prevalent and popular of data science metrics so far within soccer, it is not the only metric making an impact as data science continues to grow as an important factor in the game.

For example, building on the concept of xG is xA, expected assists, utilizing similar variables, as well as more features specific to passes, and modeling a prediction for how likely a pass is to produce a goal.  In simplistic terms, a pass which leads to a shot with a high xG would have a high xA.  However, this metric can then be used to assess passes which do not result in a shot, but could have (or, by the metric, should have) as a means of further analyzing different aspects of the flow of the game.

Top soccer clubs will always look for any edge, and as the amount of data available grows and the methods available through data science evolves, more and more metrics will emerge which can help in a deeper analysis of the game and its trends.
***
[More Blogs](https://github.com/wswager/flatiron_data_science_blog)

Wes Swager

[Github](https://github.com/wswager)

[LinkedIn](https://www.linkedin.com/in/wes-swager)
