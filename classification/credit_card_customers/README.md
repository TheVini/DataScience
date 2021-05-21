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

<details><summary>Show Dataset old size</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_002.png" height="25">
</p>
</details>

<details><summary>Show the new clean dataset</summary>
 <ul>
<li> According to this dataset author on Kaggle, two last columns must be deleted. New size: 10127 x 21.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_003.png" width="1050">
</p>
</details>

<details><summary>Show Dataset columns' analysis</summary>
<ul>
<li> Upper image shows that by getting "non-null" results, it proves that there is no null data, so there is no need to delete elements/columns or to add data by interpolation.
<li> Upper image shows that between explicative variables, there are some qualitative variables ("object" type), quantiative ones - discrete (most of them of "int64" type) and continuous (most of them of "float64"). After a deep analysis, it was noted that some variables could have their type converted from "int64" to "float64", for this context - "Total_Trans_Amt" (Total Transaction Amount) and "Total_Revolving_Bal" (Total Revolving Balance on the Credit Card). Because they represent the sum of continuous values.
<li> In the lower image, it was noticed it is necessary to apply data normalization technique to some columns.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_004.png" height="350">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_005.png" height="200">
</p>
</details>

<details><summary>Show 'Attrition_Flag' class distribution</summary>
 <ul>
<li> The response variable, 'Attrition_Flag', is unbalanced between its classes - 'Attrited Customer' and 'Existing Customer'. Then, some undersampling or oversampling technique must be applied on dataset in order to remove elements or add some synthetic elements.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_006.png" width="450">
</p>
</details>

<details><summary>Show columns' distributions analysis</summary>
 <ul>
<li> There are skewed data in some columns and it can be seen on quantitative explicative variables' histograms and on their boxplots. 
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_007.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_008.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_009.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_010.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_011.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_012.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_013.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_014.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_015.png" width="450">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_016.png" width="450">
</p>
</details>
