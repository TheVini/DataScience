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
- [1. Getting dataset from Kaggle by API]()
- [2. Exploratory Data Analysis]()
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
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_002.png" height="600">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/automobile/src/Image_003.png" height="200">
</p>
</details>
