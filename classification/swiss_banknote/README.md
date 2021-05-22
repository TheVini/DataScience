# Swiss banknote conterfeit detection

Exercise-based on a dataset published in Kaggle: https://www.kaggle.com/chrizzles/swiss-banknote-conterfeit-detection

**Goal:** Finding a model which can identify genuine and conterfeit banknotes.

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

## Table of Content
* [1. Getting dataset from Kaggle by API](#Step_1)
* [2. Exploratory Data Analysis](#Step_2)
* [3. Model training and testing - With skewed data and no attribute selection](#Step_3)
* [4. Model training with K-Fold cross-validation and testing - With skewed data and no attribute selection](#Step_4)
* [Conclusion](#Step_5)

## 1. Getting dataset from Kaggle by API

<details><summary>Show Dataset</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_001.png" width="350">
</p>
</details>

## 2. Exploratory Data Analysis

<details><summary>Show Dataset columns' analysis</summary>
<ul>
<li> By getting "non-null" results below, it proves that there is no null data, so there is no need to delete elements/columns or to add data by interpolation.
<li> The data below proves that some normalization technique is needed on explicative variables and they are also continuous.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_002.png" height="200">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_003.png" height="200">
</p>
</details>

<details><summary>Show 'conterfeit' classes distribution</summary>
<ul>
<li> The response variable, 'conterfeit', is perfect balanced between its classes. So there is no need of using undersampling or oversampling techniques.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_004.png" height="15">
</p>
</details>

<details><summary>Show explicative columns' distributions analysis</summary>
<ul>
<li> The distribution graphics below also proves that data normalization is need to some explicative variables, as well as, it shows some different kind of distributions: bimodal, normal, left and tight skewed.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_005.png" width="850">
</p>
</details>

<details><summary>Show columns' box plots analysis</summary>
<ul>
<li> The box plots below detail q few outliers.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_006.png" width="850">
</p>
</details>

<details><summary>Show QQ plots analysis</summary>
<ul>
<li> About data normality, some deatils are described below by QQ plots with alpha adjusted to 5%.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_007.png" width="850">
</p>
</details>

<details><summary>Show pairwaise correlation analysis</summary>
<p>From the heatmap of Pearson correlation described below, it can be extracted some conclusios when compare all variables to "conterfeit". According to Evans (1996 - "Evans JD (1996) Straight forward statistics for the behavioral sciences. Brooks/Cole Pub. Co, Pacific Grove", also http://leg.ufpr.br/~silvia/CE003/node74.html - in portuguese) classification for Pearson correlation, follow below the conclusions about the correlation between all variables and variable "conterfeit":</p>
<ul>
<li> Very strong: Diagonal
<li> Strong: Bottom
<li> Moderate: Left, Right, Top
<li> Very weak: Lenght
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_008.png" width="450">
</p>
</details>

<details><summary>Show Scatter and Distribution plots analysis</summary>
<ul>
<li> In addition, the Scatter and Distributions plot below show that variable "Diagonal" strongly explain the variable "conterfeit".
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_009.png" width="750">
</p>
</details>

## 3. Model training and testing - With skewed data and no attribute selection

<details><summary>Show Dataset columns example</summary>
<p>Explicative variables (left image) and response variable (right image)</p>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_010.png" height="150">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_011.png" height="150">
</p>
</details>

<details><summary>Show results' statistics</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_012.png" height="250">
</p>
</details>

<details><summary>Show results' score</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_013.png" height="250">
</p>
</details>

<details><summary>Show results' confidence interval</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_014.png" width="650">
</p>
</details>

<details><summary>Show results' ROC curve</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_015.png" height="600">
</p>
</details>

<details><summary>Show results' confusion matrix</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_016.png" height="550">
</p>
</details>

<details><summary>Show results' score distribution</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_017.png" height="450">
</p>
</details>

## 4. Model training with K-Fold cross-validation and testing - With skewed data and no attribute selection

<details><summary>Show results' statistics</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_018.png" height="250">
</p>
</details>

<details><summary>Show results' score</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_019.png" height="250">
</p>
</details>

<details><summary>Show results' confidence interval</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_020.png" width="650">
</p>
</details>

<details><summary>Show results' confusion matrix</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_021.png" height="550">
</p>
</details>

<details><summary>Show results' score distribution</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_022.png" height="450">
</p>
</details>

## 5. Conclusion

Even with no data transformation for skewed data, a good result was achieved with both algorithms during tests, section 3, using 30 train loops. But, during K-Fold cross-validation, section 4, just SVC algorithm achieved a real different result from section 3. On the 4 one, SVC reached a lower result. Other algorithms reached a good result on cross-validation, a special consideration for Logistic Regression which reached the higher result.
