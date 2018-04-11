# house-prices

Disclaimer:

This is a repository of models for predicting house prices using the Ames (Iowa, USA) dataset obtained from Kaggle:

https://www.kaggle.com/c/house-prices-advanced-regression-techniques

The dataset consists of 1460 observations (or examples) and 79 explanatory variables (or features) describing residential houses. 

We explore three different prediction models:

1. Multiple Linear Regression
2. Regression Trees
3. Neural Networks

The goal is to compare the performance of these three models.  Multiple linear regression can be considered as the baseline model.  Regression trees is typically used when a more complex, non-linear model is desired.  Like regression trees, neural networks is also used to model complex non-linear relationships, but it is more commonly used in classification problems involving big data.  

With 79 features, a considerable amount of preprocessing is involved in this project.           

### jupyter notebooks

This repository contains the following jupyter notebooks: 

1. data\_check
2. select\_features
3. final\_data_processing
4. multiple\_linear\_regression
5. regression\_trees
6. neural\_networks

Items 1-3 are preprocessing steps while 4-5 are the prediction models.  

The notebook, data\_check, is an initial look at the data; specifically, determining the amount of missing data and identifying numerical and categorical features.  Select\_features involves two major steps: identifying which features to include and imputing values.  In final\_data\_processing, the response variable  and selected features are transformed and dummy variables are created for categorical features.  

### select\_features


