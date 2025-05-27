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
- Exploratory data analysis (EDA) with Hive in Jupyter Notebook
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

## Data Visualizations, Insights and Explanations
Part of EDA is to look at the patterns and insights of the dataset and be able to tell a story. 
Throughout this analysis, several queries and visualizations were constructed with income as the common grouping variable. While this may appear repetitive at first glance, it is a deliberate approach aligned with the project’s core objective, which is to identify how different demographic and socioeconomic traits influence income levels that would be beneficial in the banking industry.
By analyzing income across variables like age, education, occupation, hours worked, and capital gain/loss, each query answers a unique question about who earns more, why, and what traits define high vs low income segments. This multi-angle analysis provides a richer, more nuanced understanding of the factors that shape earning potential, which is critical for designing data-driven strategies in banking and financial services.
Rather than repeating results, each perspective adds a new layer of insight, allowing for smarter customer segmentation, targeted financial product recommendations, and more inclusive financial planning frameworks.

### Overall Income Distribution.
![Overall Income Distributon](https://github.com/user-attachments/assets/521be4ed-21fb-4a45-af30-8734abf1210e)
Overall, the majority of the participants of this census have income less than or equal to USD 50,000. 
+ This tells us that the adults in the community of where the census was taken place belong to the middle-class income category.
+ The definition was obtained from [The Pew Research Center](https://www.pewresearch.org/short-reads/2024/09/16/are-you-in-the-american-middle-class/), which defines *"the middle class as households earning between USD 43,350 and USD 130,000. While USD 50,000 falls within the lower end of this range, it is still considered middle-class income."*

### Income by Age Group
   
   ![income_age](https://github.com/user-attachments/assets/678f6d0a-1e0b-4895-bd9f-6c598372886c)
   
   This bar chart visualizes the income distribution across age groups, using percentages within each group. The proportion of individuals earning more than USD 50,000 increases notably from the 26–35 to 46–60 age groups, meaning income peaks around mid-career. The post-60 age groups show a drop, which may reflect retirement or reduced income roles. The early adolences is seen to majoritily have income less than USD 50,000, which reflects the start of their career.

### Income by Occupation Group
   
   ![income_occu](https://github.com/user-attachments/assets/d081ff8a-f076-442a-86c9-c977c2dfbfc0)

   This chart shows the relative distribution of income groups across occupation categories. White-collar roles (eg. management, law, accounting, finance, consulting, and computer programming) dominate the >USD 50,000 bracket, while roles in admin/support, blue-collar, and service sectors are predominantly in the <USD 50,000 income group. The stark divide reveals systemic income differences tied to occupation type, which could guide banks in tailoring financial products to specific segments.

**What does this mean for banking industry?**
+ White-collar clients are most likely the candidates for credit cards with higher limits, wealth products, and home loans.
+ Service/manual labor clients may benefit more from savings tools, budget planners, or flexible microloan products.
+ Banks can also use this insight to avoid over-offering to low-income segments, preventing financial strain.

### Income by Education Group

![income_edu](https://github.com/user-attachments/assets/9c046acb-45b3-4461-a32d-605b2776d5da)

This bar graph shows that education level has a strong relationship with income potential. Most of the individuals with higher education earn above USD 50,000, while those with only primary or no formal education are almost entirely below this USD 50,000 threshold. This reinforces the importance of education in financial success and highlights a key dimension banks can use in segmentation strategies.

**What can banks do with this analysis?**
+ Banks can pre-screen or tier clients by education for financial product eligibility.
+ Individuals with no formal schooling or have only primary schooling might benefit from basic savings plans, microloans, or financial education programs.
+ Individuals with higher education can be targeted for investments, credit cards, or wealth products.

### Income by Native Region

![income_region](https://github.com/user-attachments/assets/b117ca03-e63f-4748-97be-15d57401b725)

+ The chart reveals stark regional income disparities. Individuals from North America and Europe are significantly more likely to earn above USD 50,000, while those from Central America and South America remain largely in the lower income category. 
+ These insights could be translated into regional segmentation strategies for international banking or remittance services.

### Key Traits and Patterns of Individuals with income more than USD 50,000

![top10_edu_occu](https://github.com/user-attachments/assets/8cc28c37-e94e-42cc-8a4d-105235dcf68e)

This chart highlights the top 10 education and occupation combinations across income groups. This offers valuable insight for banks that are looking to segment their customers more effectively.
+ Individuals with higher education working in white-collar roles make up a significant share of those earning more than USD 50,000, signaling strong potential for premium financial products, investment offerings, or higher credit limits.
+ Meanwhile, combinations like high school graduates in blue-collar or admin/support roles are more commonly found in the less than USD 50,000 bracket. For these segments, banks might consider offering budgeting tools, flexible loan structures, or targeted financial literacy programs to better serve their needs.

Understanding how education and occupation interact with income levels can help banks design more inclusive and data-driven financial strategies.

### How total hours worked within each job type relate to income levels?

![income_hours](https://github.com/user-attachments/assets/12fa7e0d-ff9f-4bf9-b573-915b8bf71e4b)

From the above bar chart, we can deduce that:
+ In manual labor, those earning >50K work an average of 49 hours/week, noticeably higher than most other groups. However, the increase in income is still isn’t guaranteed across the board.
+ In white-collar roles, >50K earners average 46.3 hours, which is slightly more than <=50K in the same role. So, income here seems to be less tied to effort and more to position/seniority.
+ Service and admin_support_sales jobs show almost no >50K representation — even when individuals work 34–38 hours weekly.

In banking-terms and scenario, this would translate as:
+ In lower-paying job segments with high effort, financial tools like income smoothing, flexible loan plans, or overtime bonuses would be more beneficial.
+ Meanwhile, in high-income roles, banks can look into investment products and premium services, even for individuals working “moderate” hours.

This analysis is important because it shows us that banks can’t rely on job type alone to determine earning potential and provide service according to that one particular parameter only. They would have to consider effort indicators like hours worked, as well.

### For investment purposes, what is the distribution of capital gain and capital lose against income?

![avg_cap_income](https://github.com/user-attachments/assets/340b8b24-dc84-4e5d-b7bd-4d0f8e17cf65)

The above chart visualizes the average capital gains and losses reported by income group. 

+ Individuals earning >USD50K not only report significantly higher gains, but also higher losses, which indicates more active engagement with investment instruments.
+ In contrast, <=USD50K earners show minimal capital movement, suggesting limited access to financial assets.

This pattern clearly shows that higher earners are more investment-active, which banks can use to:
+ Offer tailored wealth management or portfolio services
+ Predict which customers are ready for mutual funds, REITs, or savings-linked investments
+ Identify underserved segments who might benefit from beginner investment literacy programs or tools to grow passive income

### Key Takeaways!

+ The majority of individuals in this dataset earn ≤ USD 50,000, with income distribution heavily influenced by education level, occupation type, region, and age group.
+ Higher education combined with white-collar occupations consistently appears in the >50K category, highlighting them as prime segments for premium banking products such as investments, credit cards, or savings plans.
+ On the other hand, individuals in manual labor or service-based jobs, despite working longer average hours—remain largely in the lower income bracket. This suggests financial strain and under-compensation, calling for supportive banking strategies like budgeting tools or flexible credit offerings.
+ Capital gain and loss behavior strongly differs between income groups. High earners report significantly more capital activity, implying greater access to investment tools, which is a key signal for banks to offer wealth management services to this segment.

### Why is this analysis important to banks?
This analysis enables banks to:
+ Understand financial behaviors across demographic segments
+ Segment customers more effectively based on effort vs earnings
+ Design inclusive financial products tailored to underserved groups
+ Identify investment-readiness through indirect indicators like occupation or capital activity

**With that being said, from all this EDAs, we had pretty much fulfilled our first three objectives of the project. To make this project a lot more fruitful, I had taken one step further to build predictive models that would be beneficial for real-world banking problems. Though this dataset is an international dataset, my idea is to use this as a stepping stone to create a useful predictive model that can be applied to Malaysian data one day. This is because demographical and socioeconomical information like age, education, occupation, capital gain, capital loss, hours worked and marital status can also be obtained at the Malaysian level as well and thus, I believe this dataset and model can be a good example for Malaysian banking industry usage.**


## Predictive Modeling

As mentioned above, predictive models were then built with this dataset and the following are the insights.
I had built a KNN Model and a Logistic Regression Model and upon comparing the scores of the model, Logistic Regression Model seemed to be a much better choice for our dataset's predictive modeling and here's why.

+ **Overall Evaluation Scores:**

| Metric                  | KNN          | Logistic Regression |
|------------------------|--------------|---------------------|
| Accuracy               | 83.98%       | 85.61%              |
| Mean Squared Error     | 0.1602       | 0.1439              |
| Precision (>50K)       | 0.73         | 0.75                |
| Recall (>50K)          | 0.53         | 0.61                |
| F1-Score (>50K)        | 0.61         | 0.67                |
| AUC Score              | 0.87         | 0.90                |

+ **ROC Curve Shape:**
![Screenshot 2025-05-27 225205](https://github.com/user-attachments/assets/61090304-7cbc-448e-afd7-e7efe543ea57)

    + Both ROC curves demonstrate better-than-random classification (above the diagonal baseline).
    + The red line (Logistic Regression) hugs the top-left corner more than KNN, indicating stronger performance, especially at higher sensitivity levels.

+ **Therefore:**
    + While KNN provided decent classification, **Logistic Regression outperformed KNN** in nearly all aspects, including AUC score, precision, recall, F1-score, and overall accuracy.
    + Logistic Regression is also **more interpretable and scalable**, making it the better choice for this income classification task, especially in banking applications where understanding the reasoning behind predictions is important.

### Feature Importance from Logistic Regression Model

After choosing Logisitic Regression Model as "THE" model, I had proceeded to analysing the feature importance. This is because understanding which features influence the predictions of a logistic regression model is crucial for interpretability and model improvement. To analyze a logistic regression model and enhance its performance, one must comprehend the significance of each variable.

I had plotted the top 10 positive features to gain higher income and the top 10 negative features to gain higher income and here's what we can see.

**Strong Positive Influences:**

![Screenshot 2025-05-27 225738](https://github.com/user-attachments/assets/c7ac754c-110d-424a-90e7-4060f63a988c)

+ Age groups 46–60 and 36–45 stand out the most, suggesting mid-career individuals have higher odds of earning >USD50K.
+ Individuals with higher education shows the importance of advanced education in gaining higher income.
+ White collar and security/military occupational roles are also positively correlated.
+ Even native_region "europe" appears slightly more likely to predict high income.

**Strong Negative Influences:**

![Screenshot 2025-05-27 225825](https://github.com/user-attachments/assets/e1a7366d-94e1-41a2-ba2e-03764569d958)

+ marital_status "single", "separated" and "widowed" seems to reduce the likelihood of earning >USD50K. This could possibly due to household structure or financial stability.
+ education_grouped "primary" and occupation_grouped "manual_labor/service" also point toward lower income potential.
+ Individuals from native_region "central_america" and <18 age group unsurprisingly show negative correlation.

**What is in it for the banking industry?**
+ These traits can help banks:
    + Pre-qualify customers for credit or premium financial products.
    + Segment users by income potential for targeted campaigns.
    + Promote financial literacy or upskilling programs to lower-income segments.
 
### Prediction on New Individuals

To evaluate the robustness of the final calibrated logistic regression model, I had tested it on three hypothetical individuals with distinct demographic profiles:

| Person | Summary                                                                 |
|--------|-------------------------------------------------------------------------|
| 1️      | Higher education, white collar, 40 hrs/week, age 26–35                  |
| 2      | High school graduate, manual labor, 40 hrs/week, age 46–60              |
| 3      | No schooling, unknown occupation, 10 hrs/week, age <18                  |

The predicted income class and probabilities were:

- **Person 1**: >50K income | **Probability**: 99.9989%
- **Person 2**: >50K income | **Probability**: 99.9983%
- **Person 3**: ≤50K income | **Probability**: 0.59%

These results reflect the model's ability to **accurately differentiate income likelihood** based on relevant demographic and work-related features. It confidently assigns high-income probability to individuals with strong indicators (education, occupation, work hours), while correctly classifying the underqualified profile (Person 3) as low income.

This not only validates the model's training logic but also shows its **potential usability in real-world banking applications**, such as customer segmentation or even loan product eligibility and marketing for high net-worth services.


## Conclusion

This project took a deep dive into the UCI Adult Income dataset with the aim of uncovering patterns that influence income levels and building a predictive model that could have real-world banking applications. From identifying strong correlations between education, occupation, and region with income levels, to testing how traits like work hours and capital gain behavior contribute to earning potential, each part of this analysis had brought us closer to understanding how demographics can shape financial outcomes.

The exploratory data analysis (EDA) revealed that most individuals earn ≤ USD 50,000, with higher income typically associated with white-collar roles, advanced education, and North American or European origins. These insights have clear implications for the banking industry: they can help banks segment customers more effectively, target high-potential clients with investment products, and design more inclusive financial services for underserved groups.

The predictive modeling stage reinforced these findings. After testing both KNN and logistic regression, the logistic model emerged as the most accurate and interpretable. Not only did it perform better across all evaluation metrics, but it also provided visibility into which features most influence income, which is a critical factor for responsible and explainable AI in banking.

What makes this project even more meaningful is its transferability. While the dataset is international-based, the approach can be adapted to Malaysian data. The variables used such as age, education, marital status, occupation, and hours worked are just as available in Malaysian datasets. With some localization especially in the occupation cateogry, this model could serve as the foundation for smarter credit scoring, targeted financial products, and even predictive models that support national financial inclusion goals.

In short, while this may have started as an academic project, it offered valuable insights that could one day help banks turn demographic data into meaningful strategies, creating value across income groups and supporting more inclusive financial decision-making. It’s a small step, but one that points toward bigger possibilities.

If you're reading this, then **THANK YOU** for sticking around! I hope this would be beneficial to some out there! 




