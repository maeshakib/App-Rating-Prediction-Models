# App-Rating-Prediction-Models
 predicting app ratings using kNN-5, Random Forest, Linear Regression, and Stacking models with Orange Data Mining.

## Introductions
Global Mobile Apps Exercise - its a list of Apps in Google, Apple and Kindle store, with a lot of properties related to the Apps. The objective here is to find out whether can you predict the rating that apps get

### Summary of the data
 The dataset contains information on mobile applications from various app stores and regions. Here is a summary of the dataset:

**1.	Dataset Summary**

- Total Entries: 25,124
- Total Columns: 17

**2.	Column Descriptions: I found following columns in data set.**
- device: Type of device (tablet, smart_phone)
- t_day: Day (integer value)
- rank: Rank of the app (integer value)
- app_store: App store (e.g., Apple, Google)
- region: Region of the app.(e.g., CN, US)
- release_date: Release date of the app (e.g., 9/18/2012)
- app_age_current_version: Age of the current version of the app (integer value)
- developer: Name of the developer
- app_type: Type of app (e.g., free, paid)
- price: Price of the app (float value)
- filesize: File size of the app (float value)
•	num_screenshot: Number of screenshots (integer value)
•	rating_count: Number of ratings (integer value)
•	average_rating: Average rating (float value)
•	category: Category of the app (e.g., Education, Games)
•	in_app_ads: Presence of in-app ads (e.g., IN_APP_ADS, NO_IN_APP_ADS)
•	in_app_purchase: Presence of in-app purchases (e.g., PLUGIN_PURCHASE, NO_IN_APP_PURCHASE)

### Exploratory Data Analysis and visualizations

**1.	Distribution of Average Ratings**
With Histogram will explore the distribution of the average_rating. 
The histogram shows a significant number of apps with an average ratings of 4 and 4.5 and 5, which suggests that a large portion of the apps are well-rated.

<img  alt="Location page | PBI" width="500px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/Fig%201%20Distribution%20of%20Average%20Ratings.png" /> 
Fig 1:Distribution of Average Ratings
<br/>

**2.	Filesize vs. Average Rating**
The scatter plot shows the relationship between app filesize and average rating across different app stores (Amazon, Apple, Google Play). There is no clear correlation between filesize and average rating, indicating that app quality, as perceived by users, does not significantly depend on the app's filesize. However, apps from the Apple store (red dots) seem to have a wider range of filesizes compared to other stores.
<img  alt="Location page | PBI" width="500px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/Fig%202%20%20Filesize%20vs.%20Average%20Rating.png" />
Fig 2: Filesize vs. Average Rating
<br/>

**3.	Ratings by App Category**
Box Plot: To compare the distribution of ratings across different categories. we observed that game app getting higher ratting that other categories
<img  alt="Location page | PBI" width="500px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/Fig%203%20%20Ratings%20by%20App%20Category.png" />
Fig 3: Ratings by App Category
<br/>

**5.	Category wise Box Plot:**
 To identify outliers and understand the spread of ratings.. we observed that game app getting higher ratting that other categories
  <img  alt="Location page | PBI" width="500px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/Fig%204%20Category%20wise%20Box%20Plot.png" />
Fig 4: Category wise Box Plot
<br/>

**5.	Price vs. Average Rating**
Scatter Plot: To examine if there is any relationship between the price of the app and its rating.
   <img alt="Location page | PBI" width="500px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/Fig%204%20Category%20wise%20Box%20Plot.png" /> 

Fig 4: Price vs Average Rating

### Prediction models workflow 

  <img  alt="Location page | PBI" width="500px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/Fig%20Orange%20Data%20Mining%20process%20flow.png" />

Fig 4: Price vs Average Rating
<br/>

### Data Sampling 
There are 25,124 instances in the dataset. We used the Data Sampler widget to split the data, choosing a fixed proportion approach: 70% of the data instances were allocated to the training sample, while the remaining 30% were reserved for testing.

### Model Training

**Model Training: kNN-5**
k-Nearest Neighbors is a simple algorithm that stores all available cases and classifies new cases based on a similarity measure (e.g., distance functions). In the model training phase, we utilized the k-Nearest Neighbors (kNN) algorithm with k=5 (denoted as kNN-5)
The Random Forest model's 
Random Forest is an ensemble learning method that constructs a multitude of decision trees during training.
**Linear Regression Model:**
Linear Regression is a linear approach for modeling the relationship between a dependent variable (target) and one or more independent variables (predictors).
**Stack Model:**
Stacking is an ensemble learning technique that combines multiple classification or regression models via a meta-model. Here we are using Linear Regression, Random Forest and KNN-5 for building Stack model.
Model Evaluation on Training Data
Model Training: kNN-5
The performance metrics for this model are as follows:
•	MSE (Mean Squared Error): 0.537
•	RMSE (Root Mean Squared Error): 0.733
•	MAE (Mean Absolute Error): 0.393
•	MAPE (Mean Absolute Percentage Error): 3074...
•	R2 (R-squared): 0.329
Performance: The kNN-5 model shows moderate performance based on the given metrics. The low MSE (0.537),RMSE ( 0.733),	MAE (0.393) values suggest that the model can reasonably predict the target variable, the high MAPE and relatively low R2(0.329) indicate limitations in its predictive power and accuracy, particularly in terms of relative errors.
Weaknesses: The high MAPE value suggests that the model might struggle with predicting values accurately in percentage terms, possibly due to outliers or data with high variability. The relatively low R2 indicates that the model does not capture a significant portion of the variance in the data, implying that more sophisticated models might be needed for better performance.
The Random Forest model's 
The Random Forest model’s performance metrics are as follows:
•	MSE (Mean Squared Error): 0.070
•	RMSE (Root Mean Squared Error): 0.265
•	MAE (Mean Absolute Error): 0.142
•	MAPE (Mean Absolute Percentage Error): 0.038
•	R2 (R-squared): 0.912
**Performance:**
The low MSE (0.070), RMSE (0.265), and MAE (0.142) indicate that the model makes very accurate predictions, with small deviations from the actual values.   The MAPE (0.038) is very low, suggesting that the model's predictions are off by only 3.8% on average from the actual values, demonstrating excellent relative accuracy. The R2 value of 0.912 means that the model explains 91.2% of the variance in the target variable, showing that it effectively captures the underlying patterns in the data.

**Weaknesses:**
Training and making predictions with a Random Forest model can be computationally expensive, especially with large datasets and numerous trees. This can lead to longer training times and higher resource usage, which might be a limitation in resource-constrained environments.
Linear Regression Model:
The Linear Regression model’s performance metrics are as follows:
•	MSE (Mean Squared Error): 213900
•	RMSE (Root Mean Squared Error): 462
•	MAE (Mean Absolute Error): 42
•	MAPE (Mean Absolute Percentage Error): 8150095495280522.000
•	R2 (R-squared): -267156.112
Performance:
The high MSE (21390), RMSE (462), and MAE (42) indicate that the model makes inaccurate predictions, with substantial deviations from the actual values. The extraordinarily high MAPE (8150095495280522.000) suggests that the model's predictions are off by an extremely large percentage on average, indicating very poor relative accuracy. The negative R² value of -267156.112 means that the model performs significantly worse than simply using the mean of target variables. 
Potential Issues:
•	Model Selection: Linear Regression might not be the best choice for this dataset. It could be that the relationship between the variables is not linear.
•	Feature Selection: The features used might not be suitable, or there could be multicollinearity, where independent variables are highly correlated with each other.
•	Data Issues: There might be issues with the data, such as outliers, incorrect values, or improper scaling.
 Stack Model:
The Stack model’s performance metrics are as follows:
•	MSE (Mean Squared Error): 0.072
•	RMSE (Root Mean Squared Error): 0.268
•	MAE (Mean Absolute Error): 0.147
•	MAPE (Mean Absolute Percentage Error): 14420913682013.391
•	R2 (R-squared): 0.910
Performance:
The low MSE (0.072), RMSE (0.268), and MAE (0.147) indicate that the model makes very accurate predictions, with small deviations from the actual values. Despite the anomalously high MAPE (14420913682013.391), which seems to be an outlier, the model overall demonstrates strong performance. The high R² value of 0.910 means that the model explains 91% of the variance in the target variable, showing that it effectively captures the underlying patterns in the data.
Weaknesses: 
The extremely high MAPE value( 14420913682013.391)  suggests a significant issue, possibly due to outliers or an incorrect calculation. This metric typically measures the average absolute percentage error, and such a high value indicates that there might be instances where the model's predictions are highly inaccurate in relative terms. Investigating and addressing the source of this anomaly is crucial.


### Predictions on Test Data
 
KNN-5: The low MSE (0.329),RMSE ( 0.574),MAE (0.238) values suggest that the model can reasonably predict the target variable, the high MAPE and R2(0.589) indicate that model can predict 58% of variance of test data.
Linear Regression: The high MSE (17), RMSE (4.175), and MAE (0.515) indicate that the model makes inaccurate predictions, with substantial deviations from the actual values. The extraordinarily high MAPE suggests that the model's predictions are off by an extremely large percentage on average, indicating very poor relative accuracy. The negative R² value of -20.786 means that the model performs significantly worse than simply using the mean of target variables. 
Random Forest model: The low MSE (0.022), RMSE (0.148), and MAE (0.054) indicate that the model makes very accurate predictions, with small deviations from the actual values.   The MAPE (0.014) is very low, R2 value of 0.912 suggesting that the model explains 97.2% of the variance in the test data, model can predict, showing that it effectively captures the underlying patterns in the data.

Stack Model: The low MSE (0.020), RMSE (0.143), and MAE (0.058) indicate that the model makes very accurate predictions, with small deviations from the actual values. Despite the anomalously high MAPE which seems to be an outlier, the model overall demonstrates strong performance. The high R² value of 0.975 means that the model explains 95% of the variance in the target variable, showing that it effectively captures the underlying patterns in the data.

Discussion

Comparison of model performances.
Table comparing different metrics across model, rows column model accuracy based on column models.

 <picture>
  <img align="left" alt="Location page | PBI" width="1000px" src="https://github.com/maeshakib/App-Rating-Prediction-Models/blob/main/sumamry.png" /> <br>
</picture>
Fig: Comparison of Model performance
<br/>

### Strengths and weaknesses of each model.

1.	kNN-5:
- Strengths: Simple and easy to implement, performs well with fewer features.
- Weaknesses: High MAPE indicates poor performance, sensitive to the choice of 'k'.
2.	Random Forest:
- Strengths: Low MSE, RMSE, MAE, and MAPE, high R2, indicating excellent performance and robustness.
- Weaknesses: Can be computationally intensive, harder to interpret compared to linear models.
3.	Linear Regression:
- Strengths: Simple to implement and interpret, computationally efficient.
- Weaknesses: Extremely high MSE, RMSE, and MAPE, negative R2 indicates very poor performance and likely overfitting or data issues.
4.	Stack:
- Strengths: Lowest MSE, RMSE, high R2, indicating the best performance among the models.
- Weaknesses: Slightly higher MAE compared to Random Forest, MAPE is relatively high, indicating potential issues with percentage error.


Insights into the predictability of app ratings.
- Random Forest and Stack Models: Both demonstrate strong predictive power with high R2 values and low error metrics, suggesting that app ratings can be predicted accurately using these methods.
- kNN-5 Model: Shows moderate performance, indicating that while it can capture some patterns in the data, it is not as effective as more complex models.
- Linear Regression Model: Performs poorly, suggesting that the relationship between features and app ratings is not linear, or the model suffers from significant overfitting or underfitting.
Conclusions
In conclusion, for predicting app ratings, Random Forest and Stack models provide the best performance, with the Stack model having a slight edge in terms of overall error metrics. Both demonstrate strong predictive power with high R2 values and low error metrics, suggesting that app ratings can be predicted accurately using these methods. Slightly higher MAE compared to Random Forest, MAPE is relatively high, indicating potential issues with percentage error. Random Forest  is the best model for this data.



