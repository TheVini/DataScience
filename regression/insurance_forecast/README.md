# Medical Cost Personal Datasets

Exercise-based on a dataset published on Kaggle: https://www.kaggle.com/mirichoi0218/insurance

**Goal:** Finding a model which can accurately predict insurance costs.

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
- [1. Getting dataset from Kaggle by API](https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/README.md#1-getting-dataset-from-kaggle-by-api)
- [2. Exploratory Data Analysis](https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/README.md#2-exploratory-data-analysis)
- [3. Model training and testing]()
  * [3.1. No treatment applied on models - With skewed data and no attribute selection]()
  * [3.2. Oversampling and Undersampling Technique - With skewed data, no attribute selection, normalized data with Standard Scaler, dataset size for test 30%]()
  * [3.3. K-Fold validation and a combination of Oversampling and Undersampling techniques - With skewed data, no attribute selection, dataset size for test 30%¶]()
- [4. Conclusion]()

## 1. Getting dataset from Kaggle by API

<details><summary>Show Dataset</summary>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_001.png" width="350">
</p>
 <p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_002.png" width="100">
</p>
</details>

## 2. Exploratory Data Analysis

<details><summary>Show Dataset columns' analysis</summary>
<ul>
<li> By getting "non-null" results below, it proves that there is no null data, so there is no need to delete elements/columns or to add data by interpolation.
<li> Between explicative variables, there are some qualitative variables ("object" type), quantiative ones - discrete (most of them of "int64" type) and continuous (most of them of "float64").
<li> Afterwards, it was noticed it is necessary to apply data normalization technique to some columns.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_003.png" height="200">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_004.png" height="200">
</p>
</details>

<details><summary>Show columns' distributions and box plots analysis</summary>
 <ul>
<li> There are skewed data in some columns and it can be seen on quantitative explicative variables' histograms and on their boxplots. 
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_006.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_007.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_008.png" width="950">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_009.png" width="450">
</p>
</details>

<details><summary>Data prep for some others analysis</summary>
<ul>
<li> Encoded data
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_010.png" width="350">
</p>
</details>

<details><summary>Show pairwaise correlation analysis</summary>
 <ul>
<li> The heatmap for Pearson correlation table below proves no explicative variable is, at least, on moderate level, according to Evans classification, Evans (1996, also http://leg.ufpr.br/~silvia/CE003/node74.html, on Brazilian portuguese)
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_011.png" width="850">
</p>
</details>

<details><summary>Show Scatter and Distribution plots analysis</summary>
<ul>
<li> The first scatter plots (using Charges as hue) below show the trend seen on parwise correlation analysis.
</ul>
<ul>
<li> The second scatter plots (using Smoker as hue) below states what was seen on parwise correlation analysis.
</ul>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_012.png" width="850">
</p>
<p align="center">
  <img src="https://github.com/TheVini/DataScience/blob/master/regression/insurance_forecast/src/Image_013.png" width="850">
</p>
</details>

