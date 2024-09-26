# IBM Employee Attrition Prediction

## **Introduction**

IBM is facing a significant challenge with employee attrition, which is costly in terms of financial resources, lost knowledge, and decreased productivity. In 2019, U.S. businesses lost a trillion dollars annually due to voluntary turnover, with over 40 million workers, or 26.9% of the workforce, quitting their jobs in 2018. For IBM, reducing attrition is critical for maintaining competitiveness and sustainability. This project focuses on identifying key factors driving employee attrition and developing a predictive model using Python to help IBM proactively manage and reduce turnover efficiently.

A **best-worst scenario** for an employee who leaves a company.

|     | Best Scenario | Worst Scenario |
| --- | --- | --- |
| Cost ($) | 4,000 | 7,645 |
| Time to fill a position (days) | 42  | 52  |

---

## **Business Requirement**

1. **Best Performance Model**: The goal was to find the most effective model to predict employee attrition. The model's success was defined by its ability to identify employees who are likely to leave the company, with a focus on maximizing the recall score and, in cases where recall scores are identical, the accuracy score.
2. **Identify Key Attrition Factors**: Understanding the most important factors that contribute to employee attrition is essential for developing strategies to reduce turnover and save the company time and resources.

---

## **Process Outline**

### **Data Cleaning**

- Renamed columns to lowercase.
- Dropped unnecessary columns: 'employee_count', 'employee_number', 'job_role', 'standard_hours', 'over18'.
- Transformed categorical columns using frequency encoding: 'business_travel', 'department', 'education', 'education_field', 'marital_status'.
- Applied binary encoding to binary columns: 'gender', 'attrition', 'overtime'.

### **Prepare for Modeling**

1. **Splitting Data**: The dataset was split into features and labels, with the features consisting of all columns except attrition, and the labels being the attrition column. The data was then divided into training and testing sets.
2. **Balancing Data**: To address the imbalance in the attrition label, SMOTE was used to balance the label variable.
3. **Scaling Data:** StandardScaler() was applied to standardize the data due to differences in scale across features.

### **Modelling**

1. Five common classification models were used: KNN, Logistic Regression, Decision Trees, Random Forests, and Gradient Boosting.
2. GridSearchCV() was used for hyperparameter tuning to identify the best parameters for each model based on average recall scores.
3. Precision-recall curves and confusion matrices were analyzed to assess model performance, focusing on maximizing recall and accuracy scores.
4. The best-performing model, **Logistic Regression**, was selected based on its recall and accuracy scores.

![]()

### **Top 5 Feature**

1. After identifying Logistic Regression as the best model, feature importance was determined based on the model's coefficients.
2. Feature importance was visualized using heatmaps and bar charts for better understanding.

![]()

![]()

---

## **Conclusion**

### **Key findings**

- **Best Model:** The **Logistic Regression model** outperformed others with a recall score of 0.69 and an accuracy score of 0.76.


| Model | Recall | Accuracy |
| --- | --- | --- |
| KNN | 0.61 | 0.71 |
| **Logistic** | **0.69** | **0.76** |
| Decision Tree | 0.67 | 0.51 |
| Random Forest | 0.69 | 0.63 |
| Gradient Boosting | 0.67 | 0.67 |
<br>

- **Top 5 Feature**
  - **Stock Option Level**: lower the option level, higher the possibility to leave the company.
  - **Job Involvement**: lower the job involvement, higher the possibility to leave the company.
  - **Job Level**: lower the job level, higher the possibility to leave the company.
  - **Job Satisfaction**: lower the job satisfaction, higher the possibility to leave the company.
  - **Environment Satisfaction**: lower the environment satisfaction, higher the possibility to leave the company.


| Feature | Coefficient |
| --- | --- |
| Stock Option Level | \-0.69 |
| Job Involvement | \-0.60 |
| Job Level | \-0.58 |
| Job Satisfaction | \-0.54 |
| Environment Satisfaction | \-0.51 |
<br>

- **Business Value**
  - The model was tested on a dataset containing 294 records, successfully identifying 27 true positives and missing 12 false negatives, indicating its effectiveness in predicting employee attrition.
  - Translating to the best-worst scenario, this means:

|     | Best Scenario | Worst Scenario |
| --- | --- | --- |
| Total Loss Prevented ($) | 108,000 | 206,415 |
| Total Time Saved (days) | 1,134 | 1,404 |
<br>

### **Next Steps**

- **Enhance Stock Option Levels**: Employees with lower stock option levels are more likely to leave. Increasing stock options or providing alternative financial incentives could help retain these employees.
- **Promote Career Advancement**: Lower job levels correlate with higher attrition. IBM could address this by creating clearer career progression paths and ensuring that employees are aware of opportunities for advancement within the company.
- **Improve Overall Employee Engagement**: Job involvement, satisfaction, and environment are key to reducing attrition. IBM should enhance engagement by offering more responsibility, recognizing contributions, and providing professional development. Additionally, fostering a supportive work environment and improving work-life balance will boost satisfaction and reduce turnover.

---

## **Learning Outcome**

Throughout this project, I gained valuable insights into the process of data analysis and machine learning, particularly in the context of employee attrition. I learned how to clean and preprocess data, including techniques such as frequency encoding, binary encoding, and data scaling. I also deepened my understanding of machine learning models by applying five different classification algorithms: K-Nearest Neighbors (KNN), Logistic Regression, Decision Trees, Random Forests, and Gradient Boosting. Using GridSearchCV for hyperparameter tuning was a particularly enlightening experience, as it helped me to identify the optimal settings for each model to maximize performance. Additionally, I learned how to interpret model outputs, such as confusion matrices and precision-recall curves, to select the most effective model for predicting employee attrition.
