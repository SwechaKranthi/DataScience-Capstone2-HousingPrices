# Housing Price Prediction System
*Given the housing market frenzy in 2020-2021, We can confidently say that there is a lot of value in real estate.  Between April 2020 and April 2021, median home prices on Realtor.com [skyrocketed 17.2%](https://fortune.com/2021/09/21/home-prices-forecast-models-2022-predictions/). How much of this value is derived from pure frenzy and how much of it is inherent to a specific property is hard to tell. This project is the result of a kaggle competition that encourages data scientists to use their skills assessing a prominent problem. This housing price prediction system is a way to assess the value of a house using the data science toolset to explore the relationship between a house's features and its sale price.*

## 1. Data

Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. It is an environment that offers cool learning environments, data, and competitions for aspiring data scientists like me to grow. One such competition is the House Prices - Advanced Regression Techniques. With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home. The data of which can be accessible through the following means below:

> - [Kaggle Dataset](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data)

> - Kaggle API Command
 >   - kaggle competitions download -c house-prices-advanced-regression-techniques

> - [Original Data Set Report](http://jse.amstat.org/v19n3/decock.pdf)


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


Data Cleaning is about 50% of the task of a Data Scientist. The accuracy of a predictive model depends highly on the quality of the data you feed it. In this step, we closely understand the data and verify what sort of cleaning procedures we need to perform to improve the quality of the data set. Now, there are many ways to check for the quality of data and how to clean it, but I can boil down my cleaning process in the following steps:

- Identify and Delete That Contain a Single Value
 - almost all columns had atleast 2 distinct values. 
- Consider Columns That Have Very Few Values
  - given some columns are catagorical data, there were a few columns that have less than 7 different values in sample of 1459 rows of data. 
- Remove Columns That Have A Low Variance
 - This is an idea known as low variance filtering. As we know, Variance measures the dispersion of data realtive to its mean. Measuring the variance of different columns gives us an idea of the features that impact or not-impact our target variable - the sale price. To keep it simple, I decided to use 0 as the threshhold for low variance filter. As we know, None of the features had 0 variance or only 1 distinct value, so we didn't remove any columns. 
   - Normalizing the data is a pre-requesite to low variance filtering. It makes sure that no column is overvalued by reducing the range of all columns to a float between 0 and 1. This bring me to a potential mistake of my analysis. I standardized my data instead of normalizing due to the presence of different units of data. Standardization also works best under the assumption that the distribution of the data follows a normal bell-shaped curve. This is something we didn't check for and should be addressed in future modelling. 
- Identify and Delete that Contain Duplicate Data
  - There were no duplicates in the datasets provided by kaggle. This step can be avoided. 
- Address Missing Values 
  - I checked for counts of values that had a null value. In doing so I can determine what percentage of each feature was missing values. I then determined that any feature that had more than 50% missing values can be deemed unimportant. However, all columns were kept for further analysis to avoid loss of important variables.  We had 19 columns with some missing values. 4 of these columns had more than 50% missing values: Pool, Miscellaneous Features, Alley, Fence. I decided to replace all null values with their respective fill values. All numerical columns were either filled with mean, median or 0 as their fill value. All catagorical columns had 'None' as their fill value. 
- Dimensionality Reduction
  - this is a complication topic, so here is a reference to a good [article](https://www.analyticsvidhya.com/blog/2018/08/dimensionality-reduction-techniques-python/) on it. In simple terms, If all features are created equal and we have 5000 feautures in a given data set, how do we determine which of those features are important in predicting our target value. There are many ways of doing this, but I used my two favorites: High Correlation Filtering, and Random Forest. 
   - High Correlation Filtering is a method where we look at the coorelations between each feature and our target value. We decide to keep the once that coorelate highly with sale price. 
   - Random Forest is a regression algorithm that has built in feature importance, thus we can avoid manually selecting for features and use everything to build our model. 
- Processing Categorical & Numerical Data
 - **Numerical Data** needs to be adjusted for any skewness in it's distribution. This is to prevent misleading the models and generating wrong predictions. 
 - **Catagorical Data** is better designed for classification problems. It is hard to use catagorical data to creation regressions. To solve this problem, we encode each of our catagorical features into a series of numerical features to represent it's respective catagory. 

## 4. EDA

## 5. Algorithms

## 6. Predictions

## 7. Future Improvements

## >9000. Cliffnotes and learnings
