# DSI 8 Project 2: Ames Housing Modelling
## Executive Summary
>In this project, we investigate what is the best way for us to model and to predict sales prices of houses in Ames, IA.<br/>By drawing different models which predict from different combinations of features, we have settled on a single model with predefined parameters that will provide the best scoring in its predictions.<br/>We find that utilizing Elastic Net Regression as our modelling method, with an alpha parameter of 594.531 and an l1 ratio of 1.0, we obtain the best predictions by modelling over a set of 32 features with the top 3 features being the above grade ground living area, the overall material and finish of the house, and the neighbourhood in which the house is located.

<br/>
The steps we have taken in this project are listed below.

## Contents:
- Import and Functions
- Data Import and Cleaning
    - Faulty Data
    - Filling NA values
    - Converting Datatypes
    - Feature Name Conversion
- Data Analysis
    - Heatmap
    - Pairplot
    - One-hot Encoding
- Modelling
    - Splitting and Scaling
    - Feature Selection
    - Baseline Model
    - Regularization
        - Ridge Regularization
        - Elastic Net Regularization
- Final Model
    - Summary
    - Final Model
- Prediction
    - Import and Cleaning
    - Dummies
    - Prediction
- Postamble

---
### Imports and Functions
In this section, we list the python libraries we import for our project purposes.<br/>
We also include user-defined functions in this section to make it easy to run.<br/>
Our user-defined functions include:
- A function to fill zeroes
- A function to convert ordinal object data to integer form
- A function to obtain adjusted $R^2$ scores
- A function to obtain a list of $R^2$ scores for combinations of features in a model, and
- A function to obtain a list of adjusted $R^2$ scores for combinations of features in a model.

### Data Import and Cleaning
In this section, we identify and clean problematic data.<br/>
Our cleaning process for this project includes the following:
- Checking for any problematic datapoints. We identified one mis-typed datapoint in 'Garage Yr Built'
- Filling NA or missing values
- Converting datatypes of different features, and lastly
- Converting our feature names for future ease of use and compatibility

### Data Analysis
In this section, we create a heatmap and a pairplot to analyze relations between our features and decide on features to keep and to drop.<br/>
We drop 30 features which we either suspect have a dependence on other features, or have very little correlation with our target.<br/>
Next, we create dummy categories from our nominal features, most of which we have kept.

### Modelling
Our modelling process followed this workflow:
1. We split our data and validated the split
2. We scaled our data for future regularization purposes
3. We used Lasso Regression as a means of determining what useful features to keep
4. We generated a list of adjusted $R^2$ scores for different combinations of features and decided on the best combinations
5. We create a baseline model with Linear Regression and the combination of features we have decided on
6. We experiment with a Ridge Regression model to find if any improvements are made
7. We experiment with an Elastic Net Regression model to find if any improvements are made

### Final Model
After going through the modelling process, we decide on a final model to use for our prediction purposes.

### Prediction
We have a test set of data to predict our house sale prices for submission to our project competition in Kaggle.<br/>
In this section, we use our final model to create our predictions and export it for external submission.<br/><br/>
Our prediction process involved the following:
- Importing and cleaning the new test dataset.
- Transforming our dataset (removing features, creating dummies etc.)
- Scaling our data
- Predicting on our data with predetermined parameters from our modelling process.