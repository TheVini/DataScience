# Automobile Dataset

Exercise-based on a dataset published on Kaggle: https://www.kaggle.com/toramky/automobile-dataset

**Goal:** Finding a model which can  accurately predict car price based on some features.

**Propouse:**

- Accomplishing an exploratory data analysis on the dataset.
- Identifying and dealing with possible skewed data, where applicable.
- Accomplishing hypothesis tests by analyzing data variation, where applicable.
- Accomplishing normality tests.
- Identifying possible correlations.
- Solving possible overfitting and underfitting problems, if necessary.
- Accomplishing data normalization and coeficient regularization techniques, if necessary.
- Finding which algorithm have the best performance: Linear Regression, DecisionTreeRegressor, Lasso, GradientBoostingRegressor, Ridge, KNeighborsRegressor, PLSRegression, ElasticNet, XGBRegressor, XGBRFRegressor and RandomForestRegressor
- Applying K-Fold cross-validation.
- Validating results with confusion matrix
- Checking algorithms' results variability.

**Solution author's Linkedin profile:** https://bit.ly/3tsOnU3

## Table of Content
- [1. Getting dataset from Kaggle by API](https://github.com/TheVini/DataScience/blob/master/regression/automobile/README.md#1-getting-dataset-from-kaggle-by-api)
- [2. Exploratory Data Analysis](https://github.com/TheVini/DataScience/blob/master/regression/automobile/README.md#2-exploratory-data-analysis)
- [3. Model training and testing]()
  * [3.1. No treatment applied on models - With skewed data and no attribute selection]()
  * [3.2. Oversampling and Undersampling Technique - With skewed data, no attribute selection, normalized data with Standard Scaler, dataset size for test 30%]()
  * [3.3. K-Fold validation and a combination of Oversampling and Undersampling techniques - With skewed data, no attribute selection, dataset size for test 30%]()
- [4. Conclusion]()

## 1. Getting dataset from Kaggle by API

<details><summary>Show Dataset</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_001.png" width="1050">
</p>
</details>

## 2. Exploratory Data Analysis

<details><summary>Show Dataset columns' analysis</summary>
<ul>
<li> There is nullable columns, BUT there is another character doing the same thing, the "?", as shown in the Kaggle dataset discription, as well as many columns are described as "object" type just because this "?" represanting the nullable values, but this columns are or int64 either float64, this is not real for all "object" type columns but it is reall including for the response variable column. It proves:
<ol>
 <li> There is null data, so there is the need to delete elements/columns or to add data by interpolation, mean, or mode.
 <li> There is the need to cast some columns.
</ol>
<li> Between explicative variables, there are some qualitative variables ("object" type), quantiative ones - discrete (most of them of "int64" type) and continuous (most of them of "float64").
<li> Afterwards, it was noticed it is necessary to apply data normalization technique to some columns.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_002.png" height="500">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_003.png" height="200">
</p>
</details>

<details><summary>Show columns' distributions and box plots analysis</summary>
 <ul>
<li> There is some skewed data, it can be seen on some columns histogram and on theis boxplots below.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_004.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_005.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_006.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_007.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_008.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_009.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_010.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_011.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_012.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_013.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_014.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_015.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_016.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_017.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_018.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_019.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_020.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_021.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_022.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_023.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_024.png" width="450">
</p>
</details>

<details><summary>Show pairwaise correlation analysis</summary>
 <ul>
<li> The heatmap for Pearson correlation table below proves there is a diversity of correlation level, according to Evans classification, Evans (1996, also http://leg.ufpr.br/~silvia/CE003/node74.html, on Brazilian portuguese)
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_025.png" width="850">
</p>
</details>

<details><summary>Show Scatter and Distribution plots analysis</summary>
<ul>
<li> In pairwise relationships graphics below, it's seen that the strongest object column("num-of-cylinders") delivers a small considerable division between classes of the other variables.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_026.png" width="850">
</p>
</details>
