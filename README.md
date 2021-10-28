# Housing Price Prediction System
*Given the housing market frenzy in 2020-2021, We can confidently say that there is a lot of value in real estate.  Between April 2020 and April 2021, median home prices on Realtor.com [skyrocketed 17.2%](https://fortune.com/2021/09/21/home-prices-forecast-models-2022-predictions/). How much of this value is derived from pure frenzy and how much of it is inherent to a specific property is hard to tell. This project is the result of a kaggle competition that encourages data scientists to use their skills assessing a prominent problem. This housing price prediction system is a way to assess the value of a house using the data science toolset to explore the relationship between a house's features and its sale price.*

## 1. Data

Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. It is an environment that offers cool learning environments, data, and competitions for aspiring data scientists like me to grow. One such competition is the House Prices - Advanced Regression Techniques. With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home. The data of which can be accessible through the following means below:

> * [Kaggle Dataset](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data)

> - Kaggle API Command
 >   - kaggle competitions download -c house-prices-advanced-regression-techniques


## 2. Method

There are various ways to go about analyzing this data. Especially amongst the various tools and tricks available to data scientists ranging within AI, Neural Networks, Machine learning, It is important to classify the correct method for processing this data. So let’s break down the data first:

- What are we trying to predict?
  - We are trying to predict a numerical value (The sale price)
- Supervised or Unsupervised?
  - First, Unsupervised learning is for grouping unlabeled data into distinct groups. It is not designed for predicting outcomes. 
 - Thus our primary option ins supervised learning, but what kind?
- What kind of Supervised Learning?
  - There are 2 main types of Supervised Learning: Classification and Regression.
   - **Classification** is designed for classifying data (structured or unstructured) into distinct categories. Here, we are trying to predict, not assign a class. Regression, therefore, is the right tool for us.
   - **Regression** is a type of supervised learning that helps us learn and understand the relationship between dependent and independent variables. Here, we are trying to understand which features affect the final sale price and by how much. Hence, we will use regression as the main tool to assess the value of features and their effects on the sale price. Some data is categorical however, so we need to use some tools of classification to group certain categorical values, and the perform regression analysis on those groups of data. 

## 3. Data Cleaning 

[Data Wrangling Report](https://github.com/SwechaKranthi/DataScience-Capstone2-HousingPrices/blob/main/Notebooks/Housing_DataWrangling.ipynb)

[Pandas Profile Report](https://github.com/SwechaKranthi/DataScience-Capstone2-HousingPrices/blob/main/Reports/Housing_Data_Report.html)

## 4. EDA

## 5. Algorithms

## 6. Predictions

## 7. Future Improvements

## >9000. Cliffnotes and learnings
