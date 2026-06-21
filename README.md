# Predicting Employee Attrition with Machine Learning

## the goal of the project  

Turnover has a significant cost for each organisation. Depending on the regulations and labour law applicable in each country, replacing an employee typically costs several months of salary once recruiting, onboarding, and lost productivity are taken into account. More importantly, as Jean Emannuel Ray (2024) highlighted, for organisations, particularly those operating in the tertiary sector, « il n'est de richesse que les hommes » (there is no wealth but people). Any mistake can therefore be costly, both immediately and in the long term, financially as well as psychologically.

## Dataset

IBM HR Analytics Employee Attrition Dataset
Dataset Information : Records: 1470, Features: 35

## Attrition
Yes (1) = Employee Left
No (0) = Employee Stayed

## Methodology

1. Exploratory data analysis 
2. Feature engineering : `Overtime_distance`, `Manager_relationship`, `Stagnation`;
3. Baseline models: Logistic Regression vs Random Forest;
4. Rebalanced models (using bealanced) to improve recall on departures
5. Interpretation with SHAP

## Key results

Logistic Regression (baseline) : Accuracy = 0.86, Recall = 0.34, F1 = 0.44
Random Forest (baseline) : Accuracy = 0.85, Recall = 0.13, F1 = 0.21
Logistic Regression (balanced) : Accuracy = 0.76, Recall = 0.62, F1 = 0.45
Random Forest (balanced) : Accuracy = 0.85, Recall = 0.36, F1 = 0.43

Selected model : Logistic regression
while overall accuracy drops slightly (0.76) the recall increases (0.62), meaning that the logistic regression correctly identifies 62% of employees who are actually going to leave.

## What drives employees to leave?  (SHAP)

Overtime and distance from home: long commute combined with overtime significantly increases attrition risk (+0.37)
Manager relationship: poor management practices and a weak relationship with the manager represent one of the highest sources of turnover.
Career stagnation: employees stuck in the same role for a long time without promotion are more likely to leave

## Recommendations

Offer remote and flexible work arrangements for employees who have a long commute and a willingness to work more.
Invest in management training (soft skills) + implement 360 feedback loops to ensure effective communication.
Build internal mobility and job-rotation programs + review promotion cadence to reduce turnover.


## Limitations

Dealing with Humans means dealing with a chaotic system in a highly sensitive environment. Human behaviour is inherently unpredictable: a bad mood, indigestion, slow traffic on the way to work, or a fight with a spouse can all influence decisions in ways that are difficult to capture in a dataset.
The IBM dataset stays synthetic and may not reflect the full complexity of a real company.
SHAP was only applied to the balanced logistic regression; explanations for Random Forest or other models were not explored.



## Structure
Employee_turnover_ML_project.ipynb
README.md
dataset.csv
requirements.txt