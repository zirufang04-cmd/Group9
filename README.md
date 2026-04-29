1. Introduction

This project applies machine learning techniques to analyze and predict graduate employment outcomes and salary levels. Specifically, the study addresses two core research questions:

Can a student obtain a job placement offer?
Can the salary of employed students be accurately predicted?

The project integrates data preprocessing, exploratory data analysis (EDA), and both classification and regression modeling to evaluate the predictive power of student-related features.

2. Dataset Description

The dataset used in this project is the Student Placement and Skills Analytics Dataset (2025) obtained from Kaggle.

Total samples: 600
Total features: 13
Data categories:
Demographic information: Gender, Age
Academic information: Degree, CGPA
Experience: Internships, Projects, Certifications
Skill indicators: Technical skills, Communication skills, Aptitude score
Target variables:
Placement Offer (classification)
Salary Offered USD (regression)

3. Data Preprocessing
3.1 Data Cleaning
Standardized categorical variables (e.g., Gender, Degree)
Removed irrelevant identifier (Student ID)
Verified absence of missing values and duplicates
3.2 Feature Engineering
Binary encoding:
Gender → 0/1
Placement Offer → 0/1
One-hot encoding for Degree
3.3 Task-specific Dataset Preparation
Classification dataset: All 600 samples retained
Regression dataset: Filtered to students with placement offers (387 samples)

4. Exploratory Data Analysis (EDA)

EDA was conducted to understand data distributions and relationships between variables.

Key Observations:
Moderate class imbalance (approximately 64.5% received offers)
Salary distribution is approximately symmetric
CGPA and skill-related features show weak linear relationships with outcomes
Correlation coefficients between features and salary are close to zero

These findings suggest limited linear relationships and highlight the importance of exploring nonlinear models.

5. Methodology

The modeling framework consists of both linear and nonlinear approaches:

Linear models: Baseline performance evaluation
Nonlinear models: Capture interaction effects and nonlinear patterns

Evaluation metrics:

Classification: Accuracy
Regression: R² and RMSE

6. Classification Modeling
Models Implemented:
Logistic Regression
Decision Tree
Random Forest
Results:
Model	Training Accuracy	Testing Accuracy
Logistic Regression	63.75%	63.33%
Decision Tree	66.46%	63.33%
Random Forest	100%	62.50%
Findings:
All models achieved moderate performance (~63%)
Key influencing features include:
CGPA
Skill-related indicators
Certifications and projects
Evidence of overfitting observed in Random Forest

7. Regression Modeling
Models Implemented:
Linear Regression (OLS)
Random Forest Regression
Results:
Linear Regression: R² = -0.11
Random Forest: R² = -0.04
Interpretation:
Both models demonstrate poor predictive performance
Negative R² indicates performance worse than baseline prediction
Salary determination is influenced by unobserved variables not included in the dataset

8. Discussion
Key Insights:
Academic performance (CGPA) and general abilities show some predictive importance
Communication skills appear to be influential
Technical skills and internships show limited impact in this dataset
Explanation:

The weak predictive performance is attributed to:

Limited dataset size
Lack of important real-world variables (e.g., industry, job role, location)
Absence of feature interaction modeling

9. Limitations
Small sample size (600 observations)
Limited feature representation
Missing key determinants of salary and employment outcomes
Models do not fully capture nonlinear relationships and interactions

10. Future Work
Introduce interaction features (e.g., CGPA × Projects)
Expand dataset size and diversity
Include additional variables:
Industry
Job role
Company characteristics
Explore advanced models (e.g., boosting, neural networks)
