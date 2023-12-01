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

3. Performing EDA
General EDA was performed to get statistics of the full dataset using .describe()

Salary Increase:

Salary Increase Variables were determined to as (TotalWorkingYears, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager, PerformanceRating)
1. boxplot and kdeplot
These visuals were set up together to understand the probability distributions of each variable (the likelihood of finding data points across the range of the x axis). The resulting visuals show that majority of the variables have left skewed data.   
2. Pairplot (scatter plots)
The scatter plots were used to visualize any correlations by looking at all the data points between each combination of variable. 
3. Correlation Heatmap
The correlation heatmap was used to calculate the corelation between each combination of variable. When looking at at the PercentHike correlations, the two highest correlation values are Performance Rating and YearsAtCompany.


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


4. Regression Model - Predicting Salary Increases
Using a backwards selection process, we began by evaluating the most revelant metrics (TotalWorkingYears, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager, PerformanceRating) in a multiple regression model using the OLS models from the statsmodels library. We evaluate the model outputs and determine the significance of a variable based on if it's p-value is greater than 0.05.
After performing the multiple regression models, a model was finalized containing Years at Company and Performance Rating as the significant variables. This means that the company can use an employees tenure and their corresponding performance rating to evaluate an upcoming salary increase.  

Bonus: Classification Model - Predicting Attrition
After reviewing the dataset's variables, it was determined that the relevant metrics for predicting attrition based on context would be Gender, Age, PerformanceRating, EducationField, MonthlyIncome, OverTime. Since many of these variables are categorical datatypes, we chose to convert values using label encoding (such as gender, education field, etc).
A classification model was conducted using RandomForestClassifier. 

The results provided can be summarized as follows:  
Accuracy: The model's overall accuracy is 85% (how many times it was correct for both outcomes out of the total number of attempts).

Precision:
No's (0): The precision is 89%. Out of all the times the model predicted class 0, 89% were actually class 0.
Yes's (1): The precision is 38%. Out of all the times the model predicted class 1, only 38% were actually class 1.

In conclusion, although the overall accuracy is high, it can be misleading because of it's precision. The model can accurately predict if an employee is going to stay, but misses when trying to predict if an employee will leave. 


5. Tableau: 
A dashboard that compiled the visuals created during the EDA process has been prepared. 

Dashboard Instructions:  
Salary Increase Dashboard 
- Use the legend in the top right corner as a filter to analyze 
Attrition Dashboard 
- Use the legend in the top right corner as a filter to analyze what were the results for each variable in terms of attrition result (Yes for leaving the company or No for staying). 

Insights: 
For the Salary Increase Dashboard, it can seen be through the scatterplot that employees who got a performance rating of 3 can only get a maximum of 15% increase whereas employees who got a performance rating of 4 got at least 21-25%. The performance rating bar plot also provides information the employee's average salary increase and the gap is still present. The last plot shows a similar comparison but instead for years at the company.  
These three plots were selected because they are based on the two variables that were used in the final regression model. 

For the Attrition dashboard, the variables that were used in the attrition classification model were used. This dashboard shows how attrition can be analyzed across each of the key variables selected and the same conclusions found from the EDA process is demonstrated. 

# Challenges
Learning how to use a classification and select the right type was a challenge for both team members. If given more time, we'd like to learn more about how to interpret recall for machine learning models like the classification model. 
