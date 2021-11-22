# Employee-Churn-Predictor
Machine Learning Model to predict employee churn

# Problem Statement
You are working as a data scientist with HR Department of a large insurance company focused on sales team attrition. Insurance sales teams help insurance companies generate new business by contacting potential customers and selling one or more types of insurance. The department generally sees high attrition and thus staffing becomes a crucial aspect.

To aid staffing, you are provided with the monthly information for a segment of employees for 2016 and 2017 and tasked to predict whether a current employee will be leaving the organization in the upcoming two quarters (01 Jan 2018 - 01 July 2018) or not, given:

Demographics of the employee (city, age, gender etc.)
Tenure information (joining date, Last Date)
Historical data regarding the performance of the employee (Quarterly rating, Monthly business acquired, designation, salary)
Private Leaderboard Rank - 1
Public Leaderboard Rank - 3

# Approach
Formulating the problem as a binary classfication problem. Selection and synthesis of important features was key.

# EDA 
Check missing values, unique values by row, data type for each row etc. There were no missing values e

# Feature Engineering
Following new features are created:
* Last_Quarterly_Rating
###	Tenure_months: No. of months in the organization (‘existing’: 12-2017 – Dateofjoining; ‘Churned’ = LastWorkingDate – Dateofjoining)
###	Designation = Current Designation/Last designation before churn
###	Promotion = No.  of promotion taken in org (Designation – Joiningdesignation )
###	Avg_Quarterly_Business = Average Total Business Value for each employee per quarter
Existing Features : Gender, City, Age and Education 
Encoding/Feature Transformations

###	One-hot Encoding – Gender, City & Education
###	Label: Last_Quarterly_Rating, Designation, Promotion
###	MinmaxScaler – Avg_Quarterly_Business, Tenure_Months, Age

# Model Building
Models used :
###	Logistic Regression (Baseline)
###	Bagging : Random Forest
###	Boosting : GradientBoost, XGBoost, LightGBM, Catboost

# Model Selection:
K-fold crossvalidation
### 10-fold cross validation (LightGBM selected due to highest F1-score, avg 0.88 in training set)


