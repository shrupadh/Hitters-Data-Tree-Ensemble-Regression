# Hitters-Data-Tree-Ensemble-Regression
Tree-based regression and ensemble learning on the Hitters dataset using pruning, bagging, random forest, boosting, and LOOCV.

## Project Overview

This project applies **tree-based regression and ensemble learning methods** to the Hitters dataset to predict Major League Baseball player salaries.

The response variable is **log(Salary)**, and model performance is evaluated using **Leave-One-Out Cross-Validation (LOOCV)** and test Mean Squared Error (MSE).

## Dataset

The **Hitters dataset** contains Major League Baseball player statistics, including current-season performance, career statistics, league information, and salary.

After removing observations with missing salary values, the dataset contains:

* **263 observations**
* **19 predictors**
* **Response:** log(Salary)

Predictors include batting and career statistics such as AtBat, Hits, HmRun, Runs, RBI, Walks, Years, CAtBat, CHits, CRuns, CRBI, and CWalks, along with league and fielding information.

## Methods

The following regression methods were implemented and compared:

* Regression Tree
* Cost-Complexity Pruning
* Bagging
* Random Forest
* Gradient Boosting
* Leave-One-Out Cross-Validation (LOOCV)

## Model Performance

| Model                    | LOOCV Test MSE |
| ------------------------ | -------------: |
| Unpruned Regression Tree |         0.3318 |
| Pruned Regression Tree   |         0.2278 |
| Bagging                  |         0.1888 |
| **Random Forest**        |     **0.1800** |
| Boosting                 |         0.1928 |

**Random Forest achieved the lowest LOOCV test MSE and provided the best predictive performance among the methods evaluated.**

## Pruning Results

Cost-complexity pruning substantially reduced the complexity of the regression tree:

* Unpruned tree: **245 terminal nodes**, depth = 15
* Pruned tree: **6 terminal nodes**, depth = 3
* Optimal `ccp_alpha`: **0.01167**

Pruning reduced the LOOCV test MSE from **0.3318 to 0.2278**.

## Feature Importance

Across the ensemble models, career batting statistics were consistently among the most important predictors of log(Salary).

Important predictors included:

* **CAtBat** – Career At Bats
* **CHits** – Career Hits
* **CRuns** – Career Runs
* **CRBI** – Career Runs Batted In
* **CWalks** – Career Walks

## Conclusion

Ensemble tree methods provided better predictive performance than a single regression tree. Among all models evaluated, **Random Forest performed best with a LOOCV test MSE of 0.1800**.

The results also suggest that long-term career batting statistics are particularly informative for predicting player salary.

## Tools

* Python
* Jupyter Notebook
* pandas
* NumPy
* scikit-learn
* Matplotlib
* ISLP
