# Predicting Employee Turnover with 94% accuracy
- Analyzed historical employee attrition data from IBM to gain valuable insights into the factors influencing turnover within the organization.
- Proposed data-driven strategies to mitigate employee turnover, aiming to reduce expenses related to recruitment, hiring, training, and the potential loss of organizational progress.

# Table of Contents

1. [Introduction](#introduction)
2. [Business Understanding](#business_understanding)
3. [Data Understanding](#data_understanding)
4. [Storytelling with Tableau](#story_telling)
5. [Final Data Preparation](#data_preparation)
6. [Decision Tree](#decision_tree)
7. [Random Forest](#random_forest)
8. [Logistic Regression](#logistic_regression)
9. [Limitations](#limitations)
10. [Conclusion](#conclusion)


# Employee Attrition Analysis
Employee attrition is a crucial concern for companies as it disrupts workflow, depletes valuable resources, and incurs significant costs. On average, it costs $1,200 to recruit and train a new employee. Thus, it is imperative to understand and address the reasons behind employee turnover.

# Business Understanding
The first step in the CRISP-DM model is to establish a clear understanding of the business objectives, goals, and success criteria. This involves comprehending the reasons for employee turnover and what constitutes a successful analysis.

## Data Preparation

The next phase involves data preparation, including cleaning and exploration. Descriptive statistics, such as means and standard deviations, are calculated, and graphical representations are created to understand the dataset better.

## Data Modeling

After data preparation, data modeling is conducted. Researchers need to identify the target or independent variable for supervised learning and choose suitable machine learning techniques based on the dataset. Understanding the assumptions of each modeling technique is crucial at this stage.

## Evaluation

Models are developed and evaluated, with an iterative process between modeling and evaluation to enhance model performance.

## Deployment

Once a model is developed, knowledge and insights are presented in a format that can be used by stakeholders. Regular maintenance is scheduled to ensure the model remains accurate with new data.

# Business Understanding: The Great Resignation

The "Great Resignation" has caused labor shortages since the start of the pandemic, affecting even executive-level positions. Factors such as lack of promotion opportunities and the inability to work from home contribute to employee turnover.

## Business Objectives
- Reduce employee turnover.
- Retain employees within the company.
## Business Success Criteria
The project will be successful if the model achieves an 80% accuracy rate in predicting employee retention. Reducing false positives (predicting an employee stays when they leave) is a key focus.

## Inventory of Resources
- IT Carlow Library resources on machine learning.
- Individual project without collaborators.
- No data updates during the project.
- Hardware: Lenovo laptop.
- Software: Python and Tableau.

## Requirements, Assumptions, and Constraints

Assumptions include data verification and cleanliness.
No missing values for categorical variables; zero is considered accurate for numeric variables.
Constraints include a relatively small dataset with 1470 observations.

## Risks and Contingencies

No significant risks are foreseen, but there may be limitations due to the dataset's size.

## Abbreviations and Terminology
Abbreviations include DT (Decision Tree), RF (Random Forest), LG (Logistic Regression), SD (Standard Deviation).
Terminology includes "Leavers" (employees who left), "Stayers" (employees who stayed), True Positives, True Negatives, False Positives, and False Negatives.

## Evaluation Metrics
Evaluation includes accuracy, recall, precision, specificity, and F1 score.
ROC curve and AUC value will be used to assess model performance.

## Data Mining Goals
Predict which employees are likely to leave the company.

## Reducing False Positives Rationale
Focusing on reducing false positives is chosen to prevent the model from failing to predict employee turnover, even at the expense of increasing false negatives. It includes interventions like reducing overtime, salary raises, and hybrid work models.

## AUC and ROC

These metrics will assess the model's ability to distinguish between classes and visualize its performance.

## Recall and Precision Curve

To evaluate the performance of each model using recall and precision.

## Data Mining Success Criteria

A model is successful if it achieves a precision of 70% or higher, indicating a reduction in false positives.

## Project Plan

A project plan outlines tasks and deadlines, ensuring a steady workflow.

## Initial Assessment of Tools and Techniques
- Python 3.9 and Jupyter Notebook for data preparation, visualization, and modeling.
- Tableau for in-depth visualization.

## Research Questions
- Does working overtime increase employee attrition?
- Do specific job roles lead to higher turnover?
- Does increasing salary reduce employee attrition?
- Which model predicts employee attrition most accurately: Decision Tree, Random Forest, or Logistic Regression?

## Data Understanding
The dataset consists of past and current employees in a spreadsheet. 
Dataset was downloaded from https://www.kaggle.com/patelprashant/employee-attrition

According to Kaggle Description, the dataset was previously avaiable on IBM, however, it has been since taken down. 
https://www.ibm.com/communities/analytics/watson-analytics-blog/watson-analytics-use-case-for-hr-retaining-valuable-employees/

There are no missing values in our dataset. 

##  Data Dictionary
| Attribute | DataType |  Description |
| :- | :- | :- |
| Age | int | Age of an employee: range 18 to 60 |
| BusinessTravel | text | Travel for work: Travel_Rarely, Travel_Frequently, Non-Travel |
| DailyRate | int | Daily rate of employee salary |
| Department | text | The department that the employee worked in: Sales, Research & Development, Human Resources |
| DistanceFromHome | int | Number of *miles* away from home: range 1 to 29 |
| Education | int | The education level reached by the employee: 1 'Below College' 2 'College' 3 'Bachelor' 4 'Master' 5 'Doctor' |
| EducationField | text | The area of study: Life Sciences, Medical, Marketing, Technical Degree, Human Resources,  Other |
| EmployeeCount | int | Unclear from data dictionary |
| EmployeeNumber | int | Employee number of the employee in the dataset |
| EnvironmentSatisfaction | int | 1 'Low', 2 'Medium', 3 'High', 4 'Very High' |
| Gender | text | Gender of employee: Male or Female |
| HourlyRate | int | Hourly Rate of Employee |
| JobInvolvement | int | 1 'Low', 2 'Medium', 3 'High', 4 'Very High' |
| JobLevel | int | 1 'Low', 2 'Medium', 3 'High', 4 'Very High' |
| JobRole | text | Employee's job title: Sales Executive, Research Scientist, Laboratory Technician, Manufacturing Director, Healthcare Representative, Manager, Sales Representative, Research Director, Human Resources |
| JobSatisfaction | int | 1 'Low', 2 'Medium', 3 'High', 4 'Very High' |
| MaritalStatus | text | Employee's marital status: Single, Married, Divorced |
| MonthlyIncome | int | Employee's monthly salary |
| MonthlyRate | int | Unclear from data dictionary |
| NumCompaniesWorked | int | Number of company previously worked for |
| Over18 | text | Employee's Over-18 status: Y |
| OverTime | text | Employee's overtime status: Yes, No |
| PercentSalaryHike | int | Percent of Salary Hike |
| PerformanceRating | int | 1 'Low', 2 'Good', 3 'Excellent', 4 'Outstanding' |
| RelationshipSatisfaction | int | 1 'Low', 2 'Good', 3 'Excellent', 4 'Outstanding' |
| StandardHours | int | Unclear from data dictionary |
| StockOptionLevel | int | Unclear from data dictionary |
| TotalWorkingYears | int | Number of total working years |
| TrainingTimesLastYear | int | Number of training times last year |
| WorkLifeBalance | int | 1 'Bad', 2 'Good', 3 'Better', 4 'Best' |
| YearsAtCompany | int | Number of total working years in the company  |
| YearsInCurrentRole | int | Number of total working years in the current role |
| YearsSinceLastPromotion | int | Number of total working years since last promotion |
| YearsWithCurrManager | int | Number of total working years with current manager |

Please note: DistanceFromHome was assumed to be in miles beacuse the data is from IBm, which is an American company. This was not provided in the data dictionary.
<br></br>

#####  Data Dictionary: Target Variable
| Attribute | DataType |  Description |
| :- | :- | :- |
| Attrition | text | Did the employee leave or not: Yes or No? |


### Tableau
<div class='tableauPlaceholder' id='viz1696345448288' style='position: relative'><noscript><a href='#'><img alt='Employee Attrition ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Em&#47;Employee_Attrition_16431209161820&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Employee_Attrition_16431209161820&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Em&#47;Employee_Attrition_16431209161820&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>

# Data Preparation
Before the data was modelled, the data was processed and prepared for modelling. This include changing relevant variables to categories, levels of categories were reordered if required. After some deliberations, several variables were dropped.

#### Marital Status
Column 'MaritalStatus' was converted to a categorical variable, the categories were reordered, this becomes important in graphs. 

#### Education
Numerical values in column 'Education' was changed to corresponding categorical value, it was converted to a categorical variable and the categories were reordered, this becomes important in graphs. 

## Dropping Reduntant Columns
There are several columns that were unclear from the initial data dictionary or were too granular. Here is the table of columns dropped and the reasons for dropping them.  

| Attribute | Reason |
| :- | :- | 
| EmployeeCount | No data description was provided and all values are '1' |
| Job Level | No data description was provided |
| EmployeeNumber  | Redundant - in pandas index is used |
| Over18 | All employees are/were over 18 |
| StockOptionLevel | No data description was provided |
| PerformanceRating | Only two values: Excellent and Outstanding. Unclear what is the difference between the two |
| MonthlyRate | Too granular |
| HourlyRate | Too granular |
| DailyRate| Too granular |


## Target Variable: Attrition

The number of employees stayed in the company is more than the number of employees that left the company. 

|Attrition| # of Employees|
| :-: | :-: | 
| Stayed (No) | 1233 |
| Left (Yes) | 237 |

The dataset is unbalanced because there isn't the same number of employees in each class (stayed or left). This can make modelling difficult and inaccurate, which would rrequire upsampling or downsampling.

# Summary of Correlation, Skewness, Kurtosis, and VIF Analysis 
## Correlation Observation

There were significant correlations observed between various variables:
- YearsAtCompany and YearsInCurrentRole (r = 0.76)
- YearsAtCompany and YearsSinceLastPromotion (r = 0.62)
- YearsAtCompany and YearsWithCurrManager (r = 0.77)
- YearsInCurrentRole and YearsSinceLastPromotion (r = 0.55)
- YearsInCurrentRole and YearsWithCurrManager (r = 0.71)

## Skewness and Kurtosis

Skewness and kurtosis were examined to assess the normality of the data distribution. Skewness determines whether the data is skewed to the left or right, indicating asymmetry, while kurtosis assesses the peak of the distribution, determining whether it is too flat or too narrow. Both measures are used to identify deviations from a normal distribution, which resembles a bell curve.

The criteria for skewness and kurtosis being considered appropriate typically fall within the range of -2 to +2, as per George & Mallery (2010) and Byrne (2010).
Based on this criteria, no variables were found to significantly deviate from a normal distribution.

## Variance Inflation Factor (VIF)

Due to high correlations between certain variables, a Variance Inflation Factor (VIF) analysis was performed to assess multicollinearity. Multicollinearity can affect the significance of regression coefficients, making it challenging to determine which variable truly influences the independent variable.

The VIF analysis revealed limited multicollinearity among the variables, and no variables required removal.

## EDA Conclusion
Based on the exploratory data analysis (EDA) conducted:

The columns 'YearsWithCurrManager' and 'YearsInCurrentRole' were dropped due to their high correlations with other variables.
VIF analysis indicated limited multicollinearity, eliminating the need for further variable removal.

Skewness and kurtosis analysis showed normally distributed data, eliminating the need for additional data transformation.
Correlation and VIF analysis were revisited to confirm the handling of correlations and multicollinearity.

# Final Data Preparation 

After dropping irrelavant and highly correlated variables, there were 23 variables left with 1470 observations in the dataset. 

## Dummy Variables and Reduction
In the data preprocessing phase, categorical variables like 'Marital Status,' which had values such as 'Single,' 'Married,' and 'Divorced,' were converted into dummy variables. This process involved splitting these categorical variables into separate columns, one for each category, and assigning integer values.

For example, for 'Marital Status,' if an employee was married, a value of 1 was assigned to the 'MaritalStatus_Married' column, while 0 was assigned to the other two 'MaritalStatus' columns ('MaritalStatus_Single' and 'MaritalStatus_Divorced'). This resulted in an increase in the overall column count to 48, as evident in our 'final_data' variable.

Feature	Description	Value
| Feature | Description | Value |
|:-| :-| :- |
|BusinessTravel_Travel_Frequently| Does not travel frequently | 0 |
|BusinessTravel_Travel_Rarely | Does not travel raretly | 0 |
|BusinessTravel_Non-Travel | Does not travel | 1 |

Dummy variable reduction involves dropping one of the variables when multiple dummy variables are created for a categorical feature. In the provided example, 'BusinessTravel_Travel_Frequently' and 'BusinessTravel_Travel_Rarely' are both assigned a value of 0, indicating that 'BusinessTravel_Non-Travel' is equal to 1.

By omitting one category (in this case, 'BusinessTravel_Non-Travel'), the remaining categories are interpreted in reference to the omitted one. This practice also helps prevent multicollinearity issues in the variables.

As a result, instead of having three separate variables, only two are retained:

| Feature | Description | Value |
|:-| :-| :- |
|BusinessTravel_Travel_Frequently| Does not travel frequently | 0 |
|BusinessTravel_Travel_Rarely | Does not travel raretly | 0 |

Similar transformations were applied to other categorical variables related to 'Education,' 'Department,' 'JobRole,' and 'MaritalStatus.'


## Final Data Data Dictionary

| Attribute | DataType |  Description |
| :- | :- | :- |
| Age  | int | Age of an employee: range 18 to 60 |
| DistanceFromHome | int | Number of miles away from home: range 1 to 29 |
| JobLevel | int | Range: 1 to 5 |
| MonthlyIncome | int | Monthly Income of the Employee: Ranges from 1009 to 19999 |
| NumCompaniesWorked | int | Number of companies the employee had worked for: Ranges from 0 to 9 |
| PercentSalaryHike | int | Percentage of Salary Hike |
| TotalWorkingYears | int | Total Working Years |
| TrainingTimesLastYear | int | The number of training times last year: Ranges from 0 to 6 |
| YearsAtCompany | int | Number of years at the current company |
| YearsSinceLastPromotion | int | Number of years since last promotion: Ranges from 0 to 15|
| WorkLifeBalance | int |  Bad = 1, Good = 2, Better = 3, Best = 4 |
| EnvironmentSatisfaction  | int | Low = 1, Medium = 2, High = 3, Very High = 4 |
| JobInvolvement  | int | Low = 1, Medium = 2, High = 3, Very High = 4 |
| JobSatisfaction  | int | Low = 1, Medium = 2, High = 3, Very High = 4 |
| Gender  | Binomial | Female = 0, Male = 1 |
| OverTime  | Binomial | No = 0, Yes = 1 |
| RelationshipSatisfaction  | Binomial | No = 0, Yes = 1 |
| BusinessTravel_Non-Travel  | Binomial | No = 0, Yes = 1 |
| BusinessTravel_Travel_Frequently  | Binomial | No = 0, Yes = 1 |
| BusinessTravel_Travel_Rarely  | Binomial | No = 0, Yes = 1 |
| Department_Human Resources  | Binomial | No = 0, Yes = 1 |
| Department_Research & Development  | Binomial | No = 0, Yes = 1 |
| Department_Sales  | Binomial | No = 0, Yes = 1 |
| Education_Below College  | Binomial | No = 0, Yes = 1 |
| Education_College  | Binomial | No = 0, Yes = 1 |
| Education_Bachelor | Binomial | No = 0, Yes = 1 |
| Education_Master | Binomial | No = 0, Yes = 1 |
| Education_Doctor | Binomial | No = 0, Yes = 1 |
| EducationField_Human Resources  | Binomial | No = 0, Yes = 1 |
| EducationField_Life Sciences  | Binomial | No = 0, Yes = 1 |
| EducationField_Marketing  | Binomial | No = 0, Yes = 1 |
| EducationField_Medical  | Binomial | No = 0, Yes = 1 |
| EducationField_Other  | Binomial | No = 0, Yes = 1 |
| EducationField_Technical Degree  | Binomial | No = 0, Yes = 1 |
| JobRole_Healthcare Representative  | Binomial | No = 0, Yes = 1 |
| JobRole_Human Resources  | Binomial | No = 0, Yes = 1 |
| JobRole_Laboratory Technician  | Binomial | No = 0, Yes = 1 |
| JobRole_Manager  | Binomial | No = 0, Yes = 1 |
| JobRole_Manufacturing Director  | Binomial | No = 0, Yes = 1 |
| JobRole_Research Director | Binomial | No = 0, Yes = 1 |
| JobRole_Research Scientist  | Binomial | No = 0, Yes = 1 |
| JobRole_Sales Executive  | Binomial | No = 0, Yes = 1 |
| JobRole_Sales Representative  | Binomial | No = 0, Yes = 1 |
| MaritalStatus_Single  | Binomial | No = 0, Yes = 1 |
| MaritalStatus_Married  | Binomial | No = 0, Yes = 1 |
| MaritalStatus_Divorced  | Binomial | No = 0, Yes = 1 |



Please note: DistanceFromHome was assumed to be in miles, this was not provided in the data dictionary.

## Target Variable

| Attribute | DataType |  Description |
| :- | :- | :- |
| Attrition | Binomial | Did the employee leave or not: Yes or No? |

## Normalizing dataset
There are a lot of range betweenvariables such as Age (M = 36.92, SD = 9.13, Range = 18 - 60) and Monthly Income (M = 6 502.93, SD = 4 707.96, Range = 1 009 - 19 999) 


Due to the large variation in variables for mean and standard deviation, the data was normalised, so that each variable has a mean of 0 and a variance of 1. 
This is performed to ensure that there is equal importance placed on all the features.

If this is not performed, then the machine learning model would assume that the ‘MonthlyIncome’ was of more significance than the other variables such as 'Age' – simply because of its higher values.

## Numeric Variables
Only numeric variables were normalised such as Age and Monthly Income.

## Categorical Variables

Variables such as Gender, which were converted to 0 and 1, were excluded from normalisation because O is for Females and 1 is for Males (alphabetically assigned).

Variables that were created with dummy variables, such as MaritalStatus_Single, MaritalStatus_Married and  MaritalStatus_Divorces, also had 0 and 1 values, were excluded from normalisation because O is for No and 1 is for Yes (alphabetically assigned).

## SMOTE

The training set data is unbalanced. The majority class is No with 1029 observations, implying that the employee stayed in the company. The minority class is Yes with 441 observations, imlying the employee left the company. 
This means that data will have to be balanced. If the data was not balanced, then the model built would be good at predicting the majority, but not the minority class. 
<br></br>
It was decided to oversample due to the small number of minority class, to bring the number of YES (employee left) samples up to the level of NO (employee stayed) samples. A technique called SMOTE is used to balanced the datase: Synthetic Minority Oversampling Technique. This creates artificial samples that are similar to existing ones, and inserts them into the existing samples in the minority class. Balancing was conducted on the training data, not the test set. The algorithm needs to learn as much as it can from the training set, to be used on the test data – as this would almost always be imbalanced as in the real world. 
<br></br>
If under sampling had been undertaken instead, this would have led to a smaller number of the majority class, so less for the algorithm to learn from.
<br></br>
Stratified random sampling was used because it ensures that there is the same ratio of majority and minority class as in the whole dataset. Due to the small amount of minority class, it is vital that there is the correct ratio in test set, otherwise the models will overlearn the majority class. 
<br></br>
The results of the oversampling show that each class is now balanced: No  = 1029, Yes= 1029.

# Model
The following supervised ML classification algorithms were chosen to predict the minority class:
- Decision Tree creates a tree structure to model the relationships among the predictors and the predicted outcome (Lantz, 2015);
- Random Forest is combination of decision trees which are built on different samples of the dataset and takes their majority vote for classification (Lantz, 2015);
- Logistic Regression is very similat to linear regression which where the predictor variable is binomial (Hodeghatta and Nayak, 2016).
<br></br>

### Fine-Tuning Models
- Importance Features: During the initial built of the ML algorithm, the ML state the importance of each variable on the outcome of the target variable. This will be used to rate the importance of variables and drop them as needed to increase the accuracy of the models.

- Grid Search will be conducted using cross validation to evaluate model on a number of test sets so ensure it consistently behaves the same way.  It devides the dataset it into 5 equal folds parts), 1 will become the test set, 4 parts training set. Then it rolls again making sure that each fold becomes a test set while the others are training sets. If consistent, implies its a good model.  It will do this for each max depth of decision trees listed above it will then pick the max no: of decision trees which gives the best accurate model result.

### Features

During the process of this project, the features below were selected due to the fact that the models were built  on those specific variables. When the features that are hashed out where manually placed into the model, they were not show to be significant. It was decided to drop those features and built initial models and fine tuned from those features.  

# Decision Tree 

Decision Tree creates a tree structure to model the relationships among the predictors and the predicted outcome (Lantz, 2015);

The 'entropy' was means using 'information game' to split variables. Max depth only going to 5 levels because otherwise the model would overfit. The optimal level is unknown so it was decided to choose 5 as an experiment.

Feature imporance was also examine to establish the features that are most important in predicting which employees will leave. Variables with values 0 means they weren't use to construct the decision trees, because only level 5 was used.

### Evaluation of Decision Tree Model

After running the initial Decision Tree Model, model's accuracy was 71%.

Precision is 26% which means that the accuracy of predicting a True Negative is less than chance or a flip of unbiased coin. This means that our initial DT model is not a good at predicting true negatives and the fine tuned model needs to focus reducing false positives (reducing predicting stayers instead of leavers).

The Area Under the Curve (AUC) is 64%, which is an average marker for predicting True Positives (employees who stayed), however, the recall and the precision curve is not great at predicting True Negatives and reducing False Positives. 

### Evaluation of Cross-validation of Decision Tree
Cross-Validation is a great to examine the evaluate the accuracy of a decision tree model. The cross validation was set to score precision because our aim is to reduce False Positives. The mean cross validation score of decision tree is  73% (SD Cross Validation ± 3%), while accuracy of the fine-tuned decision Ttee model without cross validation is 77%.

Although the accuracy for cross-validation was reduced, this means that cross validation provides a better estimate of accuracy because the performance is based on unseen data. 

Recal-Precision Curve shows a very disappointing outcome at predicting recall. 

### Evaluation of Fine-Tuned Decision Tree
After dropping different variables, optimal number of varaibles was found to be 14 variables because of the high accuracy and, unfortunately, slight higher precision, which still worse than chance. 

**Significant Features**

These 14 variables were seen as the best predictors: 
- Monthly Income
- Job Satisfaction 
- MaritalStatus_Divorce
- EducationField_Medical
- MaritalStatus_Married
- BusinessTravel_Travel_Rarely
- DistanceFromHome
- TrainingTimesLastYear
- OverTime
- YearsSinceLastPromotion
<br></br>

Features that were significant were Marital Status_Divorced, age, whether the employee worked over time, studied medicine, distance from home amd the number of years since last promotion.

**Accuracy**

Even though several features were dropped and the best paramaters for DT were found, the accuracy of the fine-tuned decision tree model improved slight to 77%. 

**Precision**

Although the precision increased, it remained below the chance of a flip of unbised coin (with 30%)  which means that the fine-tuned decision tree is still fails to reduce False Positives (the employees who left but where predicted to stay).

**AUC Curves**

The AUC is 72%, which means that model is adequate at predicting True Positives (employees who stayed). Although the fine tuned DT precision-Recall curve is slightly better than the initial DT  precision-Recall curve, it still below the diagonal (which is the 50% chance). The fine tuned DT failed to adequately predict True Negatives (truly left) and False Positves (predicted to have stayed but really left).  

# Random Forest
### Evaluation of Fine-Tuned Random Forest
After dropping different variables, optimal number of varaibles was found to be 20 variables because of the high accuracy and, unfortunately, precision is still very worse than chance and, once again, we failed to meet our target of 70%. 

**Significant Features**

These 20 variables were seen as the best predictors: 
- MonthlyIncome
- MaritalStatus_Married
- JobSatisfaction
- MaritalStatus_Divorced
- JobInvolvement
- Age
- WorkLifeBalance
- DistanceFromHome
- EducationField_Medical
- BusinessTravel_Travel_Rarely
- TrainingTimesLastYear
- BusinessTravel_Non-Travel
- JobRole_Research_Scientist
- PercentSalaryHike
- YearsSinceLastPromotion
- OverTime
- Gender
- JobRole_Laboratory_Technician
- JobRole_Sales_Executive
<br></br>

Some similar features were significant in RF as DT: Marital Status_Divorced, age, whether the employee worked over time, age, studied medicine, distance from home amd the number of years since last promotion.

**Accuracy**

Even though several features were dropped and the best paramaters for DT were found, the accuracy of the fine-tuned decision tree model improved slight to 833%. 

**Precision**

Although the precision increased, it remained below the chance of a flip of unbised coin (with 47%)  which means that the fine-tuned decision tree is still fails to reduce False Positives (the employees who left but where predicted to stay).

**AUC Curves**

The AUC is 72%, which means that model is adequate at predicting True Positives (employees who stayed). Although the fine tuned DT precision-Recall curve is slightly better than the initial DT  precision-Recall curve, it still below the diagonal (which is the 50% chance). The fine tuned DT failed to adequately predict True Negatives (truly left) and False Positves (predicted to have stayed but really left).  

### Evaluation of Cross-validation of Random Forest
Cross-Validation is a great to examine the evaluate the accuracy of a random forest model. The cross validation was set to score precision because our aim is to reduce False Positives. The mean cross validation score of random forest is 92% (SD Cross Validation ± 2.5%), while accuracy of the fine-tuned decision Ttee model without cross validation is 95%.

Although the accuracy for cross-validation was reduced, this means that cross validation provides a better estimate of accuracy because the performance is based on unseen data. 

### Conclusion of Random Forest
**Accuracy**

Initial Random Forest Model accuracy was 84%. After dropping features and the grid search for the best parameters, it did not  improve, rremained at 83%. 

**Precision**

In the initial model, the precision is 50% and dropped to 44%, highlighting its inaccuracy at predicting True Negatives and reducing False Negatives. 

**Curve**

Both initial Area Under the Curve (AUC) and the fine tuned model was 72%! Unfortunately, Recall-Precision Curve failed to improve even when the model was fine tuned. 

**Overall**

Random Forest was better at predicting True Positives than Decision Tree. This is very common because Random Forest were builds several DT and votes on the most accurate DT. 

# Logistic Regression
### Evaluation of Logistic Regression
After running the initial Logistic Regression Model, model's accuracy was 78%.


Precision is 37% which means that the accuracy of predicting a True Negative is less than chance or a flip of unbiased coin. This means that our initial DT model is not a good at predicting true negatives and the fine tuned model needs to focus reducing false positives (reducing predicting stayers instead of leavers).

The Area Under the Curve (AUC) is 72%, which is an average marker for predicting True Positives (employees who stayed), however, the recall and the precision curve is not great at predicting True Negatives and reducing False Positives. 

Recal-Precision Curve shows a very disappointing outcome at predicting recall. 

## Evaluation 
We failed to reach some of our objectives.  All three fine-tuned models had high accuracy of over  75% with RF having the highest accuracy with 83% and  was build with 20 variables. However, all models failed to reduce False Positives and overfit the majority class (stayers). This means that the dataset overlearned the majority class in the training set. 

There is some relationship between job roles, salary, and working overtime increase employee turnover. It is very difficult to make a very certain clear line because of the models overlearning the majority class.  

#  Limitations and Future Suggestions
There are several limitations to this study that could explain our accuracy and high number of False Positive. 

#### Small Dataset

The best option is to collect more data. It is highly likely that since the data was collected, there have been more people who have opted to leave the company and more people have been hired. This would lead us to having a bigger dataset, which would result in better modelling, due to the small dataset with only 1,233 observations and 217 observations in minority class (employees who left).

Due to the small dataset, the training and test sets were even smaller even though upsampling using SMOTE technique was used to create more of minority class in training set artificially. This led to our data overfitting and predicting the majority class exceptionally well, however, the aim of our research is to predict the minority class well. Only 16% of the workforce left, meaning that 84% stayed, which means that if the employer does not nothing to improve workplace environment, increase salary or help employees with their work-life balance, only 16% of employees will leave and our model will continue to predict majority class well. 

#### Further Fine-Tuning the Model

There were several limitations to our models:
1. There is a possibility of binning numeric variables such as Monthly Income by examining the distribution and perhaps creating a new variable “Below Median Salary” and “Above Median Salary” to examine further whether monthly income would have more of an influence on the data. Other numerical variables such as ‘YearsatCompany’ could be divided into ‘Less than 3 years’, ‘Between 3-5 years’, ‘Between 5 – 10 years’ and ‘Above 10 years’. 
2. Once new attributes were created, redundant columns were dropped and the data was cleaned, leaving 40 attributes in the dataset. Although correlations and VIF were run, no other method was used for further feature selection to further minimise the attributes in the datasets. Features were dropped because there were not seen as significant in any of the models ran and removed. By narrowing the number of variables even further could have made the models more accurate at predicting employees who left and reduce False Positives. Some models do not handle many variables well so it would be highly recommended to further reduce the number of variables in the dataset. 
3. The SMOTE technique was used to upsample the minority class and stratifying setting was used to ensure dataset’s ratio of stayers to leavers. Finding other methods to upsample and stratifying would be highly recommended. 
4. Although the data was stratified when split into training and test data, shuffling the data was not coded into the splitting the data. This would be best practise because it is possible that during the splitting of the dataset, the training set has less employees who are lobotomy technicians than the test set. 
5. Although the models were fine-tune hyperparameters with grid search, decision tree and random forest models were not programmed to use weighted features. 

Other techniques could have been conducted to fine tune the models in Decision Tree and Random Forest such as AdaBoost Classification, Gradient Boosting, as well as Out-Of-Bag and Boostrapping. 
1. Bootstrapping is when the multiple decision trees in Random Forest are made using random sampling with replacement. This could be vital for our models to ensure that there are more samples resulting in more minority cases and more accurate True Negativ (Kunchhal, 2020).
2.	Out-of-Bag is similar to Bootstrap, however, in this method, the observations are chosen randomly and with replacement. The observations that are not in a sample are known as OUT-OF-BAG points. This could be vital for our models to ensure that there are more variety in samples, and may lead to better detection of signification variables, resulting in more accurate True Negative (predicted leavers) (Kunchhal, 2020).
3.	In AdaBoost Classification, each predictor pays more attention to wrongly predicted instances by the previous predicting model. This is achieved by changing the weights of training instances and coefficient is assigned from each predictor. This is highly depended on the predictor's training error. This would have been highly useful to us because of our target to reduce false positives (Kumara, 2020). 
4.	Gradient Boosting focuses on building accuracy by correcting of examining the previous model’s error. Although, it does not tweak the weights of training instances, it is trained by using each predecessor's residual errors as labels. It consists of the ensemble consists of N trees (Kumara, 2020).  This could be used in our case to improve True Negatives and reduce False Positives.
5.	Other evaluation metrics should have been used such as Root Mean Square Error (RMSE) which is the standard deviation of the prediction errors, also known as residuals. The error is the distance between the residuals to the regression line data points. 
6.6	No other fine-tuning was conducted on the logistic regression, which could be one of the biggest reasons why the logistic regression underperformed.  


It is highly recommended to address these needs and re-evaluating the models before deployment. Many limitations above are common practise for Data Analysts (Xu, Zhang and Li, 2011) and would make our models more accurate at predicting employees who leave. 
If these shortcomings are not addressed, then it is possible that an inaccurate model will be deployed, giving incorrect metrics that could be deployed in attempts to reduce high turnover rate, potentially damaging the reputation of the company. 

# Deployment 
Due to our results, we would highly recommend to NOT deploy these models into the working environment. The next stage should be to revise and re-evaluate HR strategies such as collect more data and examine the some issues with the dataset. 

#### Psychology of Working Environment
It is important to remember that employees motives and issues are not captured during this dataset. Even though our data visualisation analysis showed that early half of laboratory technicians left the worklplace, it did not highlight the reasons or the employee’s motives. Over half of all laboratory technicians work overtime and only 26% have left the workplace. 

Our analysis can only lead us so far because our data might not capture all issues in workplace. Perhaps, their manager was highly controlling and has created a toxic working environment that leads to employees working overtime. This might be true or false, however, this is not captured in the data and, therefore, a clear-cut reasons why laboratory technicians leave. Interviews and focus groups will have to be conducted to examine the reasons why employees resign.

Our analysis highlighted a pattern and found a relationship. Unlike other issues, this involves humans with emotions and their personal goals and motives that will have to examined to understand the real reasons why they leave. Some models were built using the employees’ marital status, finding them significant. During the initial stages when the algorithms were being built, when the marital status columns were removed, the algorithms performed worse. This could suggest that there is some sort of relationship. Perhaps, divorced employees wish to relocate to move home or having mental health issues due to the stress of the divorce, or married people wish to spend more time with their children. It is unclear what is the real reason that marital status has this an effect on the algorithms. It would be advised that the HR examines their flexibility around ‘Working From Home’.

#### Exit Interviews/ Surveys
Conducting exit interviews for employees before their leave could be a great method to highlight the reasons why the individual has decided to resign from their posts. The answers will have to analysed using thematic analysis, commonly used in psychology, and is viewed as a scientific method for analysing interviews. It would be highly recommended to use external HR manager to conduct the interview so that the leaving employee are more willing to be honest about the reasons. 

Meanwhile, surveys are quantitatively conducted, meaning that the HR managers can conduct statistical analysis in Python or Tableau to represent the data and can highlight common themes in the employees who leave.

#### Focus Group
Bi-annually HR managers should conduct focus groups to examine the common themes that occur in employee conversations. Once again, this should be conducted with an external HR manager, so that the employees are more likely to be honest. Prior to COVID-19, office perks such as free fruit and nap pods were seen as caring gestures of the FAANG (Facebook, Amazon, Apple, Netflix and  Google) (Cassidy, 2017; Shine Workplace Wellbeing, 2019). 

### Youtube - 5 mins Presentation
https://youtu.be/krjAuRgmE5Q
