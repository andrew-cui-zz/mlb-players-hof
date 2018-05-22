# mlb-players-hof: MLB Hall of Fame

Usng Lahman's Baseball Database to predict which players will be inducted into the MLB Hall of Fame.

#### Sections of the analysis
- [x] Data acquisition and wrangling
- [ ] Batter classification model (incomplete)
- [ ] Batter prediction and analysis
- [x] Pitcher classification model
- [x] Pitcher prediction and analysis

#### Dataset sources
Sean Lahman, Lahman's Baseball Database: [MLB_Kaggle](https://www.kaggle.com/seanlahman/the-history-of-baseball/data)

We limit ourselves to the following .csv files in this analysis:
- `all_star.csv`: All-Star appearances
- `batting.csv` and `pitching.csv`: Batting data and pitching data, used to evaluate player value for HOF candidacy
- `player_award_vote.csv`: MVP, Cy Young, and other votes
- `hall_of_fame.csv`: Response variable, induction into HOF
- `player.csv`: Dataset of player information to match up names, etc.

If possible, it would be interesting to incorporate the following data files in these ways:
- `postseason.csv`: World Series and postseason appearances per player
- `fielding.csv`, `fielding_outfield.csv`, `fielding_postseason.csv`, `batting_postseason.csv`, `pitching_postseason.csv`: fielding and postseason data, similar to batting
- `manager.csv`: Managerial statistics to evaluate these members for Hall of Fame status
- Counting number of times leading the league in a stat

#### Concessions and concerns with analysis
There are numerous potential issues with the analysis and classification that must be addressed:
1. Hall of Fame voting is non-stationary; the model assumes voting is consistent through over 60 years of different commitees. This simplifes our analysis greatly but is a fundamental flaw in the approach, used to get more data.
2. The models were trained solely on BBWAA voting, even though many of the current Hall of Fame members (including some that were mispredicted here) were voted in by other means.
3. Out of sample/test data fit is less indicative in this matter because of the overwhelmingly greater proportion of people who failed to make it to the Hall of Fame
4. Not all statistics have been adequately recorded, and the ways that awards were given out differed greatly over the years.
5. The players themselves changed characteristics over the years; an interesting analysis would be to look at the seasonal averages over time of different baseball traits.
6. Players were not grouped by position, or by category outside of batter/pitcher (ex: starter/reliever). This finite segmentation could lead to more effective models due to the differences that would ensue among groups in the data. Potentially clustering could have been done before that.
7. Reputation was not taken into effect in any of these cases; steroids are a key issue that have hurt many players' candidacies, but we did not have data for it.
8. Data is only up to the 2015 season, meaning my own intuition is limited to before then. Moreover, any recent stars such as Clayton Kershaw and Max Scherzer aren't included in predicting Hall of Famers because they just recently made their debuts back in that time.
9. There was very little pitcher data to validate the model on. Hold-outs could have been used alternatively; instead of Trevor Hoffman being the only out-of-sample example.
10. Classification of the model varied significantly with the model used - even slight changes in the model such as level of a decision tree would drastically impact the predictions.

#### Conclusions and reflections
Working with baseball data was fun and rewarding, between creating features such as our aggregate measures, reducing dimensionality and scaling of the data, and then this final analysis part with predicting future players. As this stands, the hitter model is incomplete even if the pitcher one is. The difficulties seen in this dataset are relatively expected, however - baseball is known for being a highly quantified sport, especially with the recent success of sabermetric-based teams like the Astros (and Billy Beane's Moneyball, the original spark of interest for baseball statistics to me), and more data will increase complexity.

Thank you to Kaggle, Sean Lahman and his dataset for providing this wealth of information. Future analysis could be to extend the prediction period, scale performance by season to avoid penalizing players with fewer seasons of experience (especially in forward-looking predictions), finite classes within the pitcher/batter categories, and reduction of the training timeframe to have a more modern BBWAA's voting used.
