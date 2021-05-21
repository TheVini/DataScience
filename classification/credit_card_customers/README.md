# Credit Card customers

Exercise-based on a dataset published in Kaggle: https://www.kaggle.com/sakshigoyal7/credit-card-customers

**Goal:** Finding a model which can predict which credit card clients are gonna get churned.

**Propouse:**

 - Accomplishing an exploratory data analysis on the dataset.
 - Identifying and dealing with possible skewed data, where applicable.
 - Accomplishing hypothesis tests by analyzing data variation, where applicable.
 - Accomplishing normality tests.
 - Identifying possible correlations.
 - Accomplishing oversampling or undersampling techniques to solve possible imbalance problem, if necessary.
 - Solving possible overfitting and underfitting problems, if necessary.
 - Accomplishing data normalization and coeficient regularization techniques, if necessary.
 - Accomplishing attribute selection, if necessary.
 - Finding which algorithm have the best performance: Naïve Bayes, Logistic Regression, Tree Decision, Random Forest, and SVC
 - Applying K-Fold cross-validation.
 - Validating results with confusion matrix
 - Checking algorithms' results variability.

**Solution author's Linkedin profile:** https://bit.ly/3tsOnU3

## 1. Getting dataset from Kaggle by API

<details><summary>Show Dataset</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_001.png" width="1050">
</p>
</details>

## 2. Exploratory Data Analysis

<details><summary>Show Dataset size</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_002.png" height="500">
</p>
</details>

<details><summary>Show Dataset clean</summary>
 <ul>
<li> according to this dataset author on Kaggle, two last columns must be deleted.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_003.png" width="1050">
</p>
</details>

<details><summary>Show Dataset columns' analysis</summary>
<ul>
<li> By getting "non-null" results below, it proves that there is no null data, so there is no need to delete elements/columns or to add data by interpolation.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_004.png" height="200">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_005.png" height="200">
</p>
</details>
