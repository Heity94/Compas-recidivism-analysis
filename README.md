# COMPAS recidivism analysis

```bash
                  Low  High
                 +---------+
Didn't Reoffend  |____|____|
Reoffended       |    |    |
                 +---------+
```

This repository contains our analysis of the **COMPAS** recidivism dataset which was published by ProPublica in their story ["Machine Bias"](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing/) story. Furthermore, we train and compare  recidivism various machine learning models to predict recidivism and use SHAP to interpret the model's behavior and check for bias.

For our project we chose to the following two prediction tasks:
1) Classification: Prediction of general recidivism within two years after COMPAS assessment
2) Regression: Prediction of the COMPAS decile score for general recidivism

## Background: ProPublica's COMPAS analysis

- ProPublica obtained a dataset of pretrial defendants and probationers from Broward County, FL, who had been assessed with the COMPAS screening system between January 1, 2013, and December 31, 2014.
- COMPAS is the name of an algorithm which was programmed to assess among others the probability of recidivism for persons facing trial
- COMPAS recidivism risk scores are based on a defendant’s answers to the COMPAS screening survey. The survey is completed by pre-trial services in cooperation with the defendant after his or her arrest.
- The COMPAS survey, at least in the ProPublica data, is typically administered the same day or the day after a person was arrested.
- For the more than 11 thousand pretrial defendants in this dataset, ProPublica then collected data on future arrests through the end of March 2016, in order to study how accurately the COMPAS score predicts recidivism for these defendants
- ProPublica collected the data from multiple sources for its study and created a database. From that database, it constructed various sub-datasets that merged and calculated various important features. For example, an indicator for a re-arrest for a new crime within two years of the original one
- ProPublica published the dataset and notebooks used in their analysis in this [GitHub repository](https://github.com/propublica/compas-analysis).

## Structure of the repository

The notebook [Classification_report](final_reports/Classification_Report_Final.ipynb) can be considered as the **main** notebook which includes (apart from the Classification modeling journey) also chapters for the analysis of ProPublica's data and the fairness discussion. The second notebook [`Regression_report`](final_reports/Regression_Report_Final.ipynb)) only contains the modeling journey for the regression task.

The general structure of this repository is detailed below
```bash
.
├── data-ProPublica               # Original datasources taken from ProPublica's repository
├── data-cleaned                  # Cleaned dataset
├── final_reports                 # Our analysis and modeling results
├── notebooks                     # Further notebooks used to explore the COMPAS dataset and create the analysis
└── original-analysis-ProPublica  # Recreation of ProPublica's original analysis in Python
```

## References
- ProPublica's story: https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing/
- ProPublica's Methodology: https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm/
- ProPublica's repository: https://github.com/propublica/compas-analysis
