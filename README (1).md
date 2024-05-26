
# **Time-Series-Forecasting**

## Project Scenario
Every company wants to increase its profit or revenue margin and customer retention is one key area industry players focus their resources. In today's world of machine learning, most companies build classification models to perform churn analysis on their customers. 

### Overview
Scenario: You are a data scientist in Corporation Favorita, a large Ecuadorian-based grocery retailer. Corporation Favorita wants to ensure that they always have the right quantity of products in stock. To do this you have decided to build a series of machine learning models to forecast the demand of products in various locations. The marketing and sales team have provided you with some data to aid this endeavor. Your team uses CRISP-DM Framework for Data Science projects


Specifically, you are to build a model that more accurately predicts the unit sales for thousands of items sold at different Favorita stores.




### Background
Wages in the public sector are paid every two weeks on the 15th and on the last day of the month. Supermarket sales could be affected by this.

A magnitude 7.8 earthquake struck Ecuador on April 16, 2016. People rallied in relief efforts donating water and other first need products which greatly affected supermarket sales for several weeks after the earthquake.


### Project Ojectives
- Perform hypothesis testing to reject or fail to reject the null hypothesis
- Develop and train a build a model that more accurately predicts the unit sales for thousands of items sold at different Favorita stores.
- Evaluate the model's performance using appropriate metrics.
- Fine-tune the model parameters to optimize performance.



### Data for the project
The training data includes dates, store, and product information, whether that item was being promoted, as well as the sales numbers. Additional files include supplementary information that may be useful in building the models

### Data Dictionary

| **Dataset** | **Description** |
|------------|-----------------|
| train.csv  | Training data containing time series of features store_nbr, family, and onpromotion, as well as the target sales. |
|            | - `store_nbr`: Identifies the store where the products are sold. |
|            | - `family`: Identifies the type of product sold. |
|            | - `sales`: Total sales for a product family at a specific store on a given date (can be fractional). |
|            | - `onpromotion`: Total number of items in a product family that were being promoted at a store on a given date. |
| test.csv   | Test data with the same features as the training data. Predict target sales for these dates. |
| transaction.csv | Contains date, store_nbr, and transactions made on specific dates. |
| sample_submission.csv | Sample submission file in the correct format. |
| stores.csv | Store metadata, including city, state, type, and cluster. |
|            | - `cluster`: Grouping of similar stores. |
| oil.csv    | Daily oil price data, including values during both the train and test data timeframes. |
| holidays_events.csv | Holidays and events data, with metadata. |



### Business Sucess Criteria
1. Improved Inventory Management: Accurate sales predictions will enable Favorita to manage inventory levels efficiently.

2. Enhanced Resource Allocation: With precise sales forecasts, Favorita can allocate human resources and logistics more effectively, ensuring that stores have adequate staff and supplies to meet customer demand.

3. Marketing and Promotion Strategies: By understanding the impact of promotions on sales, Favorita can tailor its marketing strategies to boost sales during specific periods.

4. Optimized Financial Planning: Accurate sales predictions facilitate better financial planning and budgeting.

### Future Work
Deploy the model to be used in the company's mobile/web application

## 🔅Hypothesis

Initial exploration on the data gave insight to a **null hypothesis** and its **alternative hypothesis** stated below:
- **Null Hypothesis (Ho)**: Promotional activities do not have a significant impact on sales at Corporation Favorita.


- **Alternative Hypothesis (Ha)**: Promotional activities have a significant impact on sales at Corporation Favorita.  


## Results




| Test Conducted               | Test Statistic     | P-Value                |
| ---------------------------- | ------------------ | ---------------------- |
| Independent Samples T - Test | 193.83 | 0.0000 |


Based on the hypothesis test, we obtained a very low p-value of 0.0. This indicates strong evidence to reject the null hypothesis. Therefore, we can conclude that promotional activities have a significant impact on sales for Corporation Favorita.

The test statistic of 193.83 also suggests a substantial difference in sales between promotional and non-promotional periods. These results support the notion that promotional activities play a crucial role in driving sales.

## ✍️Data Understanding
The data was pulled from the following various sources:
- data from a Github repository
- data from a OneDrive 
- data from a remote database

Data from the Github repository and SQL database data sets were used in this project for training and evaluation the machine
learning model while the last data set was used for testing the accuracy of the model.

Some additional tables acted as supplements for providing extrwa information

The major libraries used for this project were:
 1. Data manipulation: NumPy, pandas
 2. Data visualisation : Matplotlib, Seaborn, Plotly
 3. Machine learning methods : Sklearn, XGBoost
 4. Statistical models : ARIMA, SARIMA

 

## 🏋️‍♀️Data cleaning

The first phase of the cleaning aspect checked for duplicates, nulls, mismatched columns, data coherency, datatypes and column names

There were some observations which included:

- null values present in the following columns: some dates were missing
- the datatype of date being strings or integers
- there are no duplicates in the concatenated stage

 


Overall, the dataset did not need much cleaning. Key highlights of the cleaning involved:

- Converting to right datatypes
- Filling empty dates using the tools to preserve data coherency



As this project was time series based and had to be consecutive to have maximum efficiency, certain steps such as how to fill missing values as well as how to test and train data for model building differed from classic procedures.This also applies to the types of models used.





## 🔅Exploratory Data Analysis
The Exploratory Data Analysis phase delved deep into the cleaned and preprocessed datasets of the Time Series Analysis. Through a series of analytical techniques and visualizations, key insights were uncovered, shedding light on various aspects of what prompts churn. The following are some of the key insights gained from the EDA process:

Following a descriptive summary, these were some results observed:

- The train dataset contains 3,000,888 rows and 6 columns while the test dataset contains 28,512 rows and 5 columns.

- The train dataset is significantly larger than the test dataset in terms of the number of rows. This is expected, as the train dataset is usually larger to provide sufficient data for model training.

- The Holiday Events dataset contains 350 rows and 6 columns. This dataset provides information about various holidays and events.

- The Oil dataset consists of 1,218 rows and 2 columns. This dataset includes information about the daily price of oil.

- The Stores dataset contains 54 rows and 5 columns. This dataset provides details about different stores, such as their locations, types, and clusters.

- The Transactions dataset contains 83,488 rows and 3 columns. This dataset contains information about the number of transactions made at each store on specific dates.


Following **univariate and bivariate analysis**, it revealed:
- high positive skewness of the dataset
- an imbalanced dataset
- high number of outliers
- high range of values in the numerical columns prompting scaling



## 📉Data Analysis 
Visualisations were produced based on the analytical questions asked. These visuals were paramount to providing a solid foundation for analysising any trends or hitting patterns in analysing the factors contributing to churn analysis

 Business Questions
1. Is the train dataset complete (has all the required dates)?
2. Which dates have the lowest and highest sales for each year (excluding days the store was closed)?
3. Compare the sales for each month across the years and determine which month of which year had the highest sales.
4. Did the earthquake impact sales?
5. Are certain stores or groups of stores selling more products? (Cluster, city, state, type)
6. Are sales affected by promotions, oil prices and holidays?
7. What analysis can we get from the date and its extractable features?
8. Which product family and stores did the promotions affect.
9. What is the difference between RMSLE, RMSE, MSE (or why is the MAE greater than all of them?)
10. Does the payment of wages in the public sector on the 15th and last days of the month influence the store sales.

![dashboard]("../Downloads/image.png")

## 🔎Data preparation and preprocessing

With time series analysis, there are usually temporal variations in your data. Sometimes you would want to use these variations depending on your business, therefore it is crucial to understand the temporal data one can expect. The temporal data includes:

⭕Temporal variations of trend, seasonality and noise 

⭕Autocorrelation

For the study and for the types of models used, the data was made to be stationary for modeling.


## 📐Modelling

Four models were used in training the data namely:
- ARIMA 
- SARIMA
- Linear Regression
- XGBoost 


The metrics used to evaluate the performance of the models were:
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Squared Log Error (MSLE)
- Root Mean Squared Log Error (RMSLE)

## 👀Observations
After carefully assessing the performance of the models using key evaluation metrics, it is evident that the XGBoost model stands out as the most effective choice for the dataset. 

The RMSLE (Root Mean Squared Logarithmic Error) serves as a crucial indicator, and the XGBoost model achieved the lowest RMSLE of 0.0054 among all models evaluated. This indicates that the XGBoost model provides the most accurate and precise predictions when compared to ARIMA, SARIMA, and Linear Regression models.



Therefore, for this specific forecasting task, the XGBoost model will be adapted for its superior predictive accuracy.















## ✍️Conclusion and Recommendations
1. Promotion Optimization: Based on the analysis of the impact of promotions on sales, consider optimizing promotion strategies. Identify which types of promotions (e.g., discounts, BOGO offers) have the most significant influence on sales and tailor promotional campaigns accordingly. By focusing promotional efforts on what truly drives sales, you can maximize the return on investment.

2. Focus on High-Performing Cities: The top-performing city, "Quito," stands out with the highest sales. It's essential to allocate additional resources and marketing efforts to maintain and potentially increase sales in Quito. Additionally, cities like "Guayaquil," "Cuenca," "Ambato," and "Santo Domingo" have also shown strong sales performance. Consider developing city-specific strategies to capitalize on these markets.

3. Cluster-Centric Approach: The analysis reveals that certain clusters, such as "Cluster 14," "Cluster 6," and "Cluster 8," exhibit remarkable sales figures. Invest in understanding the unique characteristics of these clusters and tailor product assortments, promotions, and inventory management strategies to maximize sales potential in these areas.

4. Cross-Analysis Opportunities: Explore opportunities to combine the strengths of high-performing cities, clusters, store types, and states. For example, consider aligning promotions with holidays and events in top cities and clusters to maximize sales impact. Additionally, assess whether specific store types thrive in particular cities or clusters, and use this information to refine expansion plans.
## 🙋‍♀️Authors

- Florence Josephina Laryea
- florencelaryea@gmail.com

- [Link to my article on Medium](https://medium.com/@florencelaryea88/time-series-analysis-d19c09f6ac65)


### Co-authors

Members of Team Selenium: Bright Abu Kwarteng Snr, Success Makafui Kwawu.


## 🤗Acknowledgements

Much of our sincere gratitude goes to our instructors Racheal Appiah-Kubi and Violette Naa Adoley Allotey for their exceptional guidance, unwavering support, and invaluable mentorship throughout the course of this project.

Their expertise, dedication, and commitment to our learning journey have been instrumental in shaping our understanding and skills in data analysis


## 📚References and bibliography
Time series forecasting methods: https://www.influxdata.com/time-series-forecasting-methods/

Evaluating a Machine Learning Model: https://www.jeremyjordan.me/evaluating-a-machine-learning-model/

Hyperparameter tuning for Machine Learning Models: https://www.jeremyjordan.me/hyperparameter-tuning/