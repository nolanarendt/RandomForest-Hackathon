# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  Project 4: Hackathon Good-Fast-Cheap

-------------------

### Team Members
- Nolan Arendt
- Jessica Bow
- Peter Yonka

### Problem Statement
Given the constraint of only using a Random Forest Model, we endeavor to accurately predict if an individual makes greater than or less than $50,000 per year.

### Summary
Included in our data cleaning and model prep methodology, we dropped rows where Working Class and Occupation were both ‘?’. The remaining ‘?’ cells under Occupation were replaced with ‘Never worked’ while ‘?’ in Native Country was replaced with ‘Unknown’. Sex and Wage columns were binarized while the remaining categorical columns were dummified. We were limited to using only Random Forest modeling, although we did incorporate AdaBoosting with our Random Forest model. We created two seperate feature sets, one with the top and bottom ten most correlated features, and one that included all of the features.

### Model Scoring Summary
|Model|Feature Set|Best Parameters|Model Accuracy Score|Training Accuracy Score|Testing Accuracy Score|Improvement Over Baseline|
|---|---|---|---|---|---|---|
|Random Forest|Limited<sup>*</sup>|{max_depth: 12, n_estimators: 90}|84.9%|86.6%|85.4%|+10.3%|
|Random Forest|Full|{max_depth: 15, n_estimators: 75}|85.8%|88.5%|85.9%|+10.8%|
|AdaBoost using Random Forest|Limited<sup>*</sup>|{rf_max_depth: 4, learning_rate: 0.90, n_estimators: 90}|85.3%|86.2%|85.6%|+10.5%|
|AdaBoost using Random Forest|Full|{rf_max_depth: 4, learning_rate: 0.90, n_estimators: 90}|86.7%|88.6%|86.7%|+11.6%|

<sup>*</sup> Top 20 features with strongest positive and negative correlations

### Conclusions & Recommendations
Our baseline accuracy score was around 75.1% afer cleaning, and our best performing model has a testing score of 86.7%, and 11.6% improvment over the baseline. Without algorithm constraint, our group would like to try out different models and compare accuracy among the various models. While feature engineering appeared to be a dud, we would like to circle back and spend more time optimizing features in unique ways. Lastly, we could fine tune our models ever further given more time, such as attempting Gradient boosting and/or XGBoosting.

### Sources
Data Dictionary
 - http://cseweb.ucsd.edu/classes/sp15/cse190-c/reports/sp15/048.pdf
 - https://archive.ics.uci.edu/ml/datasets/adult

