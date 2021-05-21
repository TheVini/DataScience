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

<details><summary>Show columns' distributions and box plots analysis</summary>
 <ul>
<li> There are skewed data in some columns and it can be seen on quantitative explicative variables' histograms and on their boxplots. 
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_007.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_008.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_009.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_010.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_011.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_012.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_013.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_014.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_015.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_016.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_017.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_018.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_019.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_020.png" width="450">
</p>
</details>

<details><summary>Show pairwaise correlation analysis</summary>
 <ul>
<li> The heatmap for Pearson correlation table below proves no explicative variable is, at least, on moderate level, according to Evans classification, Evans (1996, also http://leg.ufpr.br/~silvia/CE003/node74.html, on Brazilian portuguese)
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_021.png" width="850">
</p>
</details>

<details><summary>Show Scatter and Distribution plots analysis</summary>
 <ul>
<li> Pairwise relationships graphics below proves it's going to be hard to the algorithms learning how to distinguish elements from both classes. Probably, undersampling techniques can solve this problem. Also, oversampling can solve the unbalanced data problem.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_022.png" width="850">
</p>
</details>

## 3. Data Prep

<details><summary>Data Transformation</summary>
 <ul>
<li> No transformation was applied to skewed variables, because none of them (Log and Square trasnformation) resulted in a good distribution. Analyzed columns: 'Credit_Limit', 'Avg_Open_To_Buy', 'Total_Amt_Chng_Q4_Q1', 'Total_Ct_Chng_Q4_Q1', 'Avg_Utilization_Ratio', 'Total_Trans_Amt', 'Total_Revolving_Bal'. So, RobustScaler is recommended to use in this columns during model training (see https://towardsdatascience.com/scale-standardize-or-normalize-with-scikit-learn-6ccc7d176a02).
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_023.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_024.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_025.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_026.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_027.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_028.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_029.png" width="950">
</p>
</details>

## 4. Model training

### 4.1. No treatment applied on models - With skewed data, no attribute selection, normalized data with Standard Scaler, dataset size for test 30%

<details><summary>Show results' statistics</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_030.png" height="250">
</p>
</details>

<details><summary>Show results' score</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_031.png" height="450">
</p>
</details>

<details><summary>Show results' confidence interval</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_032.png" width="550">
</p>
</details>

<details><summary>Show results' ROC curve</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_033.png" height="600">
</p>
</details>

<details><summary>Show results' confusion matrix</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_034.png" height="550">
</p>
</details>

<details><summary>Show results' score distribution</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_035.png" height="450">
</p>
</details>

### 4.2. Oversampling and Undersampling Technique - With skewed data, no attribute selection, normalized data with Standard Scaler, dataset size for test 30%

<details><summary>Undersampling analysis</summary>
<p>Some undersamping techniques were tested and the best one was the "Repeated Edited Nearest Neighbours". Undersampling techniques that were tested:</p>
<ul>
<li> Tomek Links
<li> Nearest Neighbours Technique
<li> AllKNN
<li> Condensed Nearest Neighbors
<li> Repeated Edited Nearest Neighbours
<li> One Sided Selection
<li> Neighbourhood Cleaning Rule
</ul>
</details>

<details><summary>Oversampling analysis</summary>
<p>Some oversamping techniques were tested and the best one was the "Random Over Sampler". Undersampling techniques that were tested:</p>
<ul>
<li> Random Over Sampler
<li> SMOTE
<li> ADASYN
<li> Borderline SMOTE
<li> SMOTEN
</ul>
</details>

#### 4.2.1. Combination of "Repeated Edited Nearest Neighbours" (Undersampling) and "Random Over Sampler" (Oversampling)

<details><summary>Show results' statistics</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_036.png" height="250">
</p>
</details>

<details><summary>Show results' score</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_037.png" height="450">
</p>
</details>

<details><summary>Show results' confidence interval</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_038.png" width="550">
</p>
</details>

<details><summary>Show results' ROC curve</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_039.png" height="600">
</p>
</details>

<details><summary>Show results' confusion matrix</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_040.png" height="550">
</p>
</details>

<details><summary>Show results' score distribution</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/credit_card_customers/src/Image_041.png" height="450">
</p>
</details>
