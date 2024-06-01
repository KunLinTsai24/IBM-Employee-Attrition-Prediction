# IBM Employee Attrition Prediction

## Summary
* The data originates from IBM's HR department. I utilize this dataset to determine the key factors contributing to employee turnover. To identify these factors, I formulate hypotheses for each and employ SPSS for statistical analysis, using the chi-square test for categorical variables and the independent sample t-test for continuous ones. The statistical findings provide insights into the reasons for attrition. I've processed the data for all variables. Continuous variables are standardized to negate the impact of varying scales. For binary categorical variables, I apply one-hot encoding, and for those with more than two levels, I use frequency encoding. This encoding simplifies the model. I then employ these factors to develop various machine learning models such as logistic regression, LDA, KNN, random forest, and decision tree. After partitioning the data into training and test sets, I  address the issue of imbalanced samples to mitigate potential biases. The optimal model is chosen based on a confusion matrix that maximizes true positives and minimizes false negatives, indicating its superior predictive capability for identifying potential departures. The logistic regression model proves to be the best. Using the true positive rate, I estimate the potential cost and time savings for IBM. Ultimately, the model could result in savings ranging from 136,000 to 259,930 and a time reduction of 1,428 to 1,768 days.

## Situation
* In mid-2019, Gallup reported that U.S. businesses were losing a trillion dollars annually due to voluntary employee turnover. The U.S. Bureau of Labor Statistics also highlighted that over 40 million American workers, representing 26.9% of the workforce, quit their jobs in 2018. For individual organizations, the cost of replacing an employee can be significant, ranging from half to twice the employee's annual salary.
* A **best-worst scenario** for an employee who leaves a company.

|                                  | Best scenario | Worst scenario |
|----------------------------------|---------------|----------------|
| **Cost \($\)**                       | 4,000          | 7,645           |
| **Time to fill a position \(days\)** | 42            | 52             |

## Task
* The primary objective was to determine the factors that cause attrition and build a machine learning model to identify employees most likely to leave. This would help in curbing turnover costs and ensuring a more engaged workforce.
* When building a machine learning model, I focus on **sensitivity** and then **classification error**, that is, **minimizing the False Negatives while maximizing the True Positives**.

## Action
### Hypothesis Testing <BR>
* This is part of Hypothesis Testing <BR>
![](https://github.com/KunLinTsai24/IBM-Employee-Attrition-Prediction/blob/main/img/Hypothesis.jpg)

### Confusion Maxtrix <BR>
* Confusion Matrix of the best model (Logistic model) <BR>
![](https://github.com/KunLinTsai24/IBM-Employee-Attrition-Prediction/blob/main/img/Confusion%20Matrix.png)

### Best-Worst Scenario Analysis <BR>

|                                  | Best scenario | Worst scenario |
|----------------------------------|---------------|----------------|
| **Cost \($\)**                   | 4,000         | 7,645          |
| **Time to fill a position \(days\)** | 42        | 52             |

* Testing the model using a data set containing 294 records, it was able to correctly identify 34 (True Positives) and miss 13 (False Negatives) from a total of 47 employees who tend to leave. Translating to the best-worst scenario, this means:

|                                  | Best scenario | Worst scenario |
|----------------------------------|---------------|----------------|
| **Total loss prevented \($\)**   | 136000        | 259930         |
| **Total time saved \(days\)**    | 1428          | 1768           |


* In addition, **without the model**, the company would have 47 employees that could leave, translating it to **a total loss of \$ 188,000 in the best scenario and \$ 359,315 in the worst scenario**.

### Top Five Factors
* Top five factors of employee attrition <BR>
![](https://github.com/KunLinTsai24/IBM-Employee-Attrition-Prediction/blob/main/img/Top%20Five%20Factors.jpg)


## Result
* The best model is the logistic regression model, which could result in savings ranging from 136,000 to 259,930 and a time reduction of 1,428 to 1,768 days.
* The top five factors are monthly income, age, total working years, distance from home, and years at the company.
