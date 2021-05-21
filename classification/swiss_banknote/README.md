## Swiss banknote conterfeit detection

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

### 1. Getting dataset from Kaggle by API

<details><summary>Show Dataset</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_001.png" width="350">
</p>
</details>

### 2. Exploratory Data Analysis

**Analysis:** 
 - By getting "non-null" results below, it proves that there is no null data, so there is no need to delete elements/columns or to add data by interpolation.
 - The data below proves that some normalization technique is needed on explicative variables and they are also continuous.

<details><summary>Show Dataset columns' analysis</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_002.png" height="250">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_003.png" height="250">
</p>
</details>

**Analysis:** 
 - The response variable, 'conterfeit', is perfect balanced between its classes. So there is no need of using undersampling or oversampling techniques.
<details><summary>Show 'conterfeit' classes distribution</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_004.png" height="25">
</p>
</details>

**Analysis:** 
 - The distribution graphics below proves that data normalization is need to some explicative variables, as well as, it shows some different kind of distributions: bimodal, normal, left and tight skewed.
<details><summary>Show columns' distributions</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/classification/swiss_banknote/src/Image_005.png" width="350">
</p>
</details>
