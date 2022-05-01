Credit Scoring Classification
=============

Petit example of credit scoring analysis based on the 
[data mining course](http://www.lsi.upc.edu/~belanche/Docencia/mineria/mineria.html) of my former PhD adviser Tomas Aluja

------------

## About the dataset

The raw dataset contains 4455 rows and 14 columns:

<table>
<tbody>
<tr><td><b>1  Status</b></td> <td>credit status</td></tr>
<tr><td><b>2  Seniority</b></td> <td>job seniority (years)</td></tr>
<tr><td><b>3  Home</b></td> <td>type of home ownership</td></tr>
<tr><td><b>4  Time</b></td> <td>time of requested loan</td></tr>
<tr><td><b>5  Age</b></td> <td>client's age </td></tr>
<tr><td><b>6  Marital</b></td> <td>marital status </td></tr>
<tr><td><b>7  Records</b></td> <td>existance of records</td></tr>
<tr><td><b>8  Job</b></td> <td>type of job</td></tr>
<tr><td><b>9  Expenses</b></td> <td> amount of expenses</td></tr>
<tr><td><b>10 Income</b></td> <td> amount of income</td></tr>
<tr><td><b>11 Assets</b></td> <td> amount of assets</td></tr>
<tr><td><b>12 Debt</b></td> <td> amount of debt</td></tr>
<tr><td><b>13 Amount</b></td> <td> amount requested of loan</td></tr>
<tr><td><b>14 Price</b></td> <td> price of good</td></tr>
</tbody>
</table>

## Methodology

In this [project](https://github.com/gregoryoffodum/Credit-Risk-Score-Classification/blob/main/Credit%20Scoring.ipynb), Decision Tree, Random Forest and XGBoost models have been used to predict customer credit defaulting behaviour. 

Decision trees learn if-then-else rules from data, find the best split and select the least impure split. This algorithm can overfit, that's why we control it by limiting the max depth and the size of the group.

Random forest combines multiple decision trees. It should have a diverse set of models to make good predictions.

Gradient boosting trains model sequentially: each model tries to fix errors of the previous model. XGBoost is an implementation of gradient boosting.

## Results

- Decision Tree (DT), Random Forest (RF) and XGBoost models (XGB) gave roc_auc_scores of 76%, 82% and 83% respectively.  
- After parameter tuning, best maximum depth for DT to avoid overfitting was found to be 6. Best RF parameters were max depth of 10, and minimum sample leaf of 10.
- After tuning, best XGB parameters were learning rate of 0.1, maximum depth and minimum child weight of 3 and 1 respectively.
- XGBoost gave the best performance and was used as final model to train data.

