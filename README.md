# STQD6324 Data Management Assignment: UCI Adult Income Dataset

## Introduction
Hi and Welcome to my repository! In this project, we would be looking at the UCI Adult Income dataset, also known as the "Census Income" dataset, which is a classic resource used for predictive modeling and demographic analysis. The dataset contains detailed information about individuals including age, workclass, education level, occupation, and native country, and is commonly used to determine factors that influence whether a person earns more than USD 50,000 annually.

In the context of this assignment, the dataset was selected due to its realistic data inconsistencies, variety of attribute types, and potential for meaningful exploratory data analysis (EDA).

The project consists of:
- Data Cleaning using Python
- Exploratory Data Analysis using Apache Hive
- Data Visualization using Python (matplotlib, Seaborn)
- Insights & Explanations
- Recommendations based on studies
- Conclusion

## Dataset Overview
The UCI Adult Income dataset contains demographic and employment data used to predict whether a person earns more than $50K/year. It includes attributes such as age, workclass, education, occupation, and native country.

- **Rows**: 32,561 (raw), 32,537 (after cleaning)
- **Columns**: 15 (raw), 18 (after cleaning + grouping)
- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/adult)

## Data Cleaning

### Issues Identified
- Missing values represented by `'?'`
- Inconsistent casing and spacing
- Duplicate rows
- Categorical values with redundant or unclear labels

### Cleaning Actions
- Replaced `'?'` with `NaN`, then imputed.
- Trimmed whitespaces, lowercased categorical values
- Removed 24 fully duplicated rows
- Standardized and grouped categorical columns:
  - `education` → `education_grouped`
  - `occupation` → `occupation_grouped`
  - `native_country` → `native_region`

## Data Visualizations


## Insights and Explanations


## Recommendations


## Conclusion

