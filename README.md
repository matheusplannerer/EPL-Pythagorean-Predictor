# EPL-Pythagorean-Predictor

This is the first assignment in the course: Foundations of Sports Analytics: Data, Representation, and Models in Sports by University of Michigan.

In this project we are looking at the relationship between team win percentage and Pythagorean expectation using data from the English Premier League (EPL) 2017/18 season. For this they provided an Excel datafile (EPL2018-18.xlsx) containing all match results for the 2017/18 season (380 games).

These are the project's steps:

1. Load the datafile (this contains 6 variables: the date, home team, away team, goals scored (FTHG), goals against (FTAG) andthe result (H- home win, D- draw, A – away win).

2. Create a value for a home wins (win= 1, draw=0.5, loss= 0) and away wins and a count variable for each game (=1).

3. Create a file for games played in 2017 (before date 20180000) and another one for games played in 2018 (after date 20180000).
For the 2017 games, use .groupby to create a dataframe aggregating by home team the variables for count, home wins, goals for and goals against.  Then, use .groupby to  create a separate dataframe aggregating by away team the variables for count, away wins, goals for and goals against. Rename the variables to denote whether they are aggregates for home team or away team.

4. Then merge the home and away dataframes.

5. Sum the values of home and away wins, games, goals for and goals against, then create the values for win percentage (wpc) and the Pythagorean expectation (pyth). 

6. Repeat steps 3-5 for the 2018 games. Be sure to give different names for wpc and pyth in 2017 and 2018.

7. Now merge 2017 and 2018 summary files.

8. Now generate a correlation matrix for the wpc and pyth variables for 2017 and 2018

# Results
Chart 1: Pythagorean Expectation (2017) against win percentage in the second half of the season

![image](https://user-images.githubusercontent.com/45919662/155887356-5964e6af-0254-4de9-8ed5-77420c04e51a.png)

Chart 2: Win percentage from the first half of the season against win percentage in the second half

![image](https://user-images.githubusercontent.com/45919662/155887385-f4c23c8a-3db0-4308-8c0f-d8515f40e339.png)

Table 1: Correlation coefficients comparison

![image](https://user-images.githubusercontent.com/45919662/155887393-a870a5ea-6ecc-42c3-b897-efb5595dab4a.png)

# Conclusion
We can see from the correlation matrix that win percentage in the second half of the season is correlated with win percentage in the first half of the season - the correlation coefficient is +0.757. It's not surprising that performance in the first half of the season is to an extent predictive of performance in the second half. But there are also clearly things that can change.

We could simply use first half win percentage as a predictor of second half win percentage, but when we look at the correlation matrix we can see that the Pythagorean Expectation is an even better forecast - the correlation coefficient is higher, at +0.796. To be sure, the difference is not large, but it is slightly better. This was, in fact, the initial impetus for Bill James when introducing the statistic. He argued that a win could ride on lucky hit and the difference of just one run, which made wins a less reliable predictor than the aggregate capacity to produce runs and limit conceding runs. As in many aspects of baseball analysis, our data show that James was quite right.
