# house-prices

This is a repository of models for predicting house prices using the Ames (Iowa, USA) dataset from Kaggle:

https://www.kaggle.com/c/house-prices-advanced-regression-techniques

The dataset consists of 1460 observations (or examples) and over 70 explanatory variables (or features) describing residential houses. 

We explore three different prediction models:

1. Multiple Linear Regression
2. Tree-based models: Regression Tree, Random Forests, and Boosted Trees
3. Neural Networks

The goal is to compare the performance of these three models.  Multiple linear regression can be considered as the baseline model.  A regression tree is typically used when a more complex, non-linear model is desired.  Random Forests and Boosted Trees create a better prediction model than a single regression tree by using an ensemble or sequence of trees.  Like tree-based models, neural networks is also used to model complex non-linear relationships, but it is more commonly used in classification problems involving big data.         

## jupyter notebooks

This repository contains the following jupyter notebooks: 

1. data\_check
2. select\_features
3. final\_data_processing
4. multiple\_linear\_regression
5. regression\_trees (will upload by May)
6. neural\_networks (will upload by April)

Items 1-3 are preprocessing steps while 4-5 are the prediction models.  

The notebook, data\_check, is an initial look at the data to gain some insight; specifically, to determine the amount of missing data and identify numerical and categorical features.  Select\_features involves two major steps: identify which features to include in the analyses and impute values.  In final\_data\_processing, the response variable  and selected features are transformed and dummy variables are created for categorical features.  

### on data processing

A considerable amount of data preprocessing is involved for this dataset because there are many features.  This project is approximately 80% data processing and 20% modeling.  We describe some feature processing that were performed. See the notebook, select_features, for more details.   

Some categorical features had many categories and with few observations in some of the categories.  For example, the feature MSZoning had the following categories (and percentage of observations): RL (79%), RM (15%), FV (4%), RH (1%), and C (all) (< 1%).  In order for the models to perform well by detecting the effects or contributions of each category, we create a new category for those with few observations called OthZone (for other zone).  Thus, we create one category for FV, RH, and C (all). In the analysis, the feature, MSZoning will have three categories with the new created category having at least 5% of the observations.  

In some cases, categories were combined to reduce the total number of categories.  For example, in the HouseStyle feature, the categories, 1.5Fin and 1.5Unf were combined into the single category, 1.5Story.  

There were several categories for the feature, Neighborhood, and modeling it as is may inhibit the performance of the model, because many subcategories have low counts and the sample size may not be large enough.  A new feature was created called Quadrant (four categories) which described the location of the neighborhood relative to the axes formed by the main roads, Grand Ave (North-South) and Lincoln Way (East-West).  The values for Quandrant were estimated by the author based on the Ames, Iowa map and searches for the exact locations of the neighborhoods. The idea behind this feature engineering is that the analysis of general regions (the quandrants) that may be highly correlated may contribute more useful information to the analysis.   

Features that had large amounts of data missing were excluded.  Values of features with missing data roughly less than 20% were imputed.  For example, observations with missing values for MSZoning were included in the new created category, OthZone.  For continuous features such as YearBuilt, missing values were imputed as 1971, the overall mean of all YearBuilt values.  

## using the notebooks

With many features in the dataset, the input data need to be analysis-ready. The jupyter notebooks for preprocessing input data facilitate the analyses.  If an input data has missing values, the notebook, select\_features, determines whether to exclude or impute these values.  If a value belongs to a feature category that is low count, then select\_features, assigns the value to an appropriate category. Thus, one only has to input the data for preprocessing (via select\_features and final\_data\_processing) and the output data will be converted into an analysis-ready dataset that can be analyzed by the prediction models.

In the modeling notebooks the training data is split into 70% training and 30% validation sets.  When feeding the test dataset, select\_features and final\_data\_processing have to be modified slightly: (1) change the name of the files to retrieve and save and (2) in final\_data\_processing, there is no SalePrice (the quantity you are predicting), therefore, lines of codes involving this variable need to be commented out. 

## results

### 1. multiple linear regression

For the multiple linear regression model, the log-scale mean square validation error (MSE) was 0.14957.  House prices were also predicted for a Kaggle test set consisting of 1,459 observations.  When submitted to Kaggle, the test MSE was 0.13642 which was ranked 1,841 out of 4,676 entries on April 11, 2018.  Not bad for an initial simple model!  

I also worked with a team on this same dataset at the New York Data Science Academy Bootcamp (Cohort 13) as part of our Machine Learning project.  See our blog post here:

https://nycdatascience.com/blog/student-works/machine-learning/an-interpretable-prediction-model-for-house-prices/

### 2. tree-based models (to follow)

### 3. neural networks (to follow)
