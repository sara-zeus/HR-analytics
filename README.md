# MidtermProject

# Project Goal:
The goal of this project is to demonstrate data analysis techniques such as data cleaning and performing EDA using Python along with producing dashboards to present business solutions.    

# Business Problem:
Using a HR dataset provided by IBM, we will address the following questions: 
1. What metrics can be used to help predict an employee's upcoming salary increase? 

Bonus: Classification Model - Predicting Attrition 


# Process and Results
1. Upload Dataset

2. Quality Assurance Process: 
The following checks/transformations were completed: 
- General Review (i.e formatting, understanding values, etc)
- Checking Null counts on all columns
- Validating Age (applying reasonable limits on age columns)
- Reviewing Appropriate Datatypes
- Checking for duplicates in EmployeeID
- Dropped irrelevant columns (i.e only 1 value such EmployeeCount containing 1's and StandardHours containing 80's)
- Transformations: PercentColumns were converted into decimal formats. During Models, categorical data was converted using label encoding. 

2. Performing EDA
General EDA was performed to get statistics of the full dataset using .describe()

Salary Increase:

Salary Increase Variables were determined to as (TotalWorkingYears, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager, PerformanceRating)
1. boxplot and kdeplot
These visuals were set up together to understand the distribution of each salary variable in relation to the salaryhike. The resulting visuals show that majority of the variables have left skewed data.   
2. Pairplot (scatter plots)
3. Correlation Heatmap
Both the pairplot and correlation visuals were used to to understand the overall correlation of each variable. Looking at the PercentHike correlations, the two highest correlation values are Performance Rating and YearsAtCompany.


Attrition 

1. What is the breakdown of attrition in terms of gender, age, performance rating? 
2. Which Education Field is more likely to leave? 
3. Does income impact attrition?  
4. Does overtime impact attrition?   

Each of the visuals show how each categorical datatype has different results in terms of which category has a higher likelyhood of staying or leaving the company. 
Results: 
Gender: There is double the amount of men leaving the company in comparison to women. 
Age: As employees reach retirement ages (i.e. past 55) the rate of leaving the company reduces. Most employees leave during their late 20's or early 30s. 
Performance Rating: The ratio of employees who leave with a high performance rating is much less than those who have a 3 rating. 
Education Field: The major that has the most people staying is life sciences, but also has the highest total turnover.   
Income: People who left the company had lower average salaries than those who stayed at the company.
Overtime: A key takeaway is that when employees are working overtime, they're more likely to leave the company than stay. 


3. Regression Model - Predicting Salary Increases
Using a backwards selection process, we begin by evaluating the most revelant metrics (TotalWorkingYears, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager, PerformanceRating) in a multiple regression model using the OLS models from the statsmodels library. We evaluate the model outputs and determine the significance of a variable based on if it's p-value is greater than 0.05.
After performing the multiple regression models, a model was finalized containing Years at Company and Performance Rating as the significant variables. This means that the company can use an employees tenure and their corresponding performance rating to evaluate an upcoming salary increase.  

Bonus: Classification Model - Predicting Attrition
After reviewing the dataset's variables, it was determined that the relevant metrics for predicting attrition based on context would be Gender, Age, PerformanceRating, EducationField, MonthlyIncome, OverTime. Since many of these variables are categorical datatypes, we chose to convert values using label encoding (such as gender, education field, etc).
A classification model was conducted using   



Tableau: 
A dashboard that compiled the visuals created during the EDA process has been prepared. For the attrition dashboard, it allows the user to interpret the relevant categories based on selecting an attrition value (Yes for leaving the company or No for staying). 

Refer to the Dashboard Instruction Document on how to use the dashboard. 