# Premier-League-Prediction
STAT-155: Final Project
# Home Advantage in the Premier League

Final project for an introductory statistics course analyzing home-field advantage in the English Premier League using logistic regression, exploratory data analysis, and predictive modeling in R.

## Overview

This project investigates whether home teams have a measurable advantage over away teams in the Premier League. Using match statistics from the 2020–2021 season, we analyzed factors such as:

* Shots
* Shots on target
* Corners
* Fouls
* Team accuracy
* Halftime results

As part of our statistics final project, we built logistic regression models to predict match outcomes and evaluate which variables significantly affect a home team’s probability of winning.

## Research Question

> Do home teams have an advantage over away teams in the Premier League?

## Key Findings

* Home teams won **42.89%** of matches compared to **33.95%** for away teams.
* Home teams leading at halftime won nearly **90%** of those matches.
* Shots on target were the strongest statistically significant predictors of match outcome.
* The final logistic regression model achieved:

  * **Accuracy:** 88.33%
  * **Sensitivity:** 79.75%
  * **Specificity:** 86.64%

## Technologies Used

* **R**
* **RStudio**
* Logistic Regression (`glm`)
* Exploratory Data Analysis
* Confusion Matrices
* Likelihood Ratio Tests
* Statistical Inference

## Dataset

The dataset was sourced from Premier League match statistics and published on Kaggle after cleaning by Ewan Gomer.

Relevant variables included:

* Full-time home goals
* Full-time away goals
* Home/away shots
* Home/away shots on target
* Home/away corners
* Match outcome
* Halftime winner

## Methodology

We used a logistic regression model where:

* The dependent variable was match outcome (`winner`)
* Predictors included:

  * Home goals
  * Total shots
  * Shots on target
  * Home accuracy
  * Away accuracy
  * Halftime winner

The model tested whether these variables significantly influenced the probability of a home-team victory.

## Example Model

```r
model <- glm(
  winner ~ FTHG + TotalShots + ShotsOT +
  HTA + ATA + HT_winner,
  data = soccer,
  family = "binomial"
)
```

## Results

### Significant Predictors

| Variable             | Effect on Home Win Probability |
| -------------------- | ------------------------------ |
| Home Shots on Target | +69%                           |
| Away Shots on Target | -41%                           |
| Halftime Lead        | Strong positive relationship   |

### Confusion Matrix

| Actual / Predicted | 0   | 1   |
| ------------------ | --- | --- |
| 0                  | 188 | 29  |
| 1                  | 33  | 130 |

## Limitations

This study does not account for:

* Crowd effects
* Travel fatigue
* Stadium familiarity
* Psychological factors
* Referee tendencies

These variables may influence home advantage but are difficult to quantify empirically.

## Contributors

* Misha Awan
* Neko Henderson
* Tyler Smith
* Jorge Mico-Crump

## References

* Richard Pollard (2008) — *Home Advantage in Football*
* Novillo et al. (2024) — *A Multilayer Network Framework for Soccer Analysis*
* ESPN Match Statistics
* World Soccer Talk Premier League Viewership Data

## Future Improvements

Potential next steps include:

* Adding expected goals (xG)
* Including referee and attendance data
* Using machine learning models such as random forests or XGBoost
* Expanding analysis across multiple seasons
