# STQD6324 Data Management Assignment: UCI Adult Income Dataset

## Introduction
Hi and Welcome to my repository! In this project, we would be looking at the UCI Adult Income dataset, also known as the "Census Income" dataset, which is a classic resource used for predictive modeling and demographic analysis. The dataset contains detailed information about individuals including age, workclass, education level, occupation, and native country, and is commonly used to determine factors that influence whether a person earns more than USD 50,000 annually.

In the context of this assignment, the dataset was selected due to its realistic data inconsistencies, variety of attribute types, and potential for meaningful exploratory data analysis (EDA).

Even though the UCI Adult Income dataset wasn’t originally built for banking use, the kind of demographic information it contains is actually super relevant to the industry. Income, education level, occupation, and even country of origin are the kind of traits banks use to segment customers, assess risk, and decide who gets offered what. By analyzing these patterns, banks can figure out which groups are underserved, who might be eligible for premium products, or even where to focus financial literacy efforts. So while this project is rooted in data management, it also shows how insights like these could shape real-world decisions in a banking context.

## Objectives
- To analyze income distribution across demographic groups such as age, education, occupation, and region.
- To identify key traits and patterns associated with individuals earning above USD 50,000 annually.
- To uncover disparities that may highlight underserved or high-potential segments within a banking context.
- To build a predictive model that estimates the likelihood of an individual earning above USD 50,000 based on their demographic profile.
- To explore how demographic-based income prediction can inform customer segmentation and financial decision-making in the banking industry.

## Scope of Work
This project includes:
- Data cleaning and preprocessing using Python
- Exploratory data analysis (EDA) with Hive and Zeppelin
- Visualization of income patterns across demographic attributes
- Predictive modeling using logistic regression and decision trees
- Interpretation of model performance and features
- Banking-related insights and real-world application

## Dataset Overview
The UCI Adult Income dataset contains demographic and employment data used to predict whether a person earns more than $50K/year. It includes attributes such as age, workclass, education, occupation, and native country.

- **Rows**: 32,561 (raw), 32,537 (after cleaning)
- **Columns**: 15 (raw), 16 (after cleaning + grouping)
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

