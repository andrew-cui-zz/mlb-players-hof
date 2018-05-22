# mlb-players-hof: MLB Hall of Fame

Usng Lahman's Baseball Database to predict which players will be inducted into the MLB Hall of Fame. This is for data wrangling; afterwards, we will run an analysis to predict future HOF'ers (grading against the 2015-2018 classes) and run some visualizations as well.

#### Dataset sources:   
Sean Lahman, Lahman's Baseball Database: [MLB_Kaggle](https://www.kaggle.com/seanlahman/the-history-of-baseball/data)

We limit ourselves to the following .csv files in this analysis:
- `all_star.csv`: All-Star appearances
- `batting.csv` and `pitching.csv`: Batting data and pitching data, used to evaluate player value for HOF candidacy
- `player_award_vote.csv`: MVP, Cy Young, and other votes
- `hall_of_fame.csv`: Response variable, induction into HOF
- `player.csv`: Dataset of player information to match up names, etc.

If possible, it would be interesting to incorporate the following data files in these ways:
- `postseason.csv`: World Series and postseason appearances per player
- `fielding.csv`, `fielding_outfield.csv`, `fielding_postseason.csv`, `batting_postseason.csv`, `pitching_postseason.csv`: Fielding and postseason data, similar to batting
- `manager.csv`: Managerial statistics to evaluate these members for Hall of Fame status
- Counting number of times leading the league in a stat
