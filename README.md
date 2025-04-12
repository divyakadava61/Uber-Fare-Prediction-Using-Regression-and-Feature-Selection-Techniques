# Uber-Fare-Prediction-Using-Regression-and-Feature-Selection-Techniques
The project is about the world’s largest taxi company, Uber Inc. In this project, we are looking to predict the fare for their future transaction cases. Uber delivers services to millions of customers daily. Now, it becomes really important to manage their data properly to come up with new business ideas and achieve the best results. Eventually, it becomes crucial to estimate the fare prices accurately. This dataset mostly revolves around the New York demographic, but there are some other trips as well. With the help of the variables in our dataset, we want to understand what factors are contributing to the mean change in ‘Fare’.
## Data Dictionary
 - ID- a unique identifier for each trip
 - fare- the cost of each trip in usd
 - pickup_datetime- date and time when the meter was engaged
 - passenger_count- the number of passengers in the vehicle (driver entered value)
 - pickup_longitude- the longitude where the meter was engaged
 - pickup_latitude- the latitude where the meter was engaged
 - dropoff_longitude- the longitude where the meter was disengaged
 - dropoff_latitude- the latitude where the meter was disengaged
## GOALS
 Our primary goals are to:
 1. Build a good prediction model to forecast the fare of an Uber ride.
 2. Determine which attributes are significant in predicting the Uber fare.
 3. Address the question: “Does pickup_datetime have a significant linear relationship with fare?”
The third question is particularly interesting because a key attribute missing from our dataset is the ‘Number of drivers’ present at the time of ‘pick up.’ A reasonable assumption would be that if the demand for rides is higher at a particular time than the supply of drivers in that locality, the fare should increase. The number of drivers could vary throughout the day; for example, at 2 am, while the number of drivers is reduced, potential riders are also less, resulting in lower demand and, consequently, lower fare for Uber. On the other hand, during peak hours, such as 4-5 pm, the demand for Uber might increase. Although the number of available drivers is higher, the high demand could lead to higher fares. Therefore, given the lack of data for the number of available drivers at pickup time, we want to investigate whether pickup time plays a significant role in the increase or decrease of fare.
## Process
In this analysis, we began by cleaning the dataset—removing redundant columns, converting pickup_datetime into numerical features, handling missing values, and calculating distances using the Haversine formula. Despite fitting an initial linear model, the R² was extremely low, prompting further investigation into high-leverage and influential points. To better capture the underlying patterns, we narrowed the data to January 2013 and applied robust regression methods. Ultimately, a Weighted Least Squares (WLS) model was built after feature selection using techniques like AIC, BIC, and adjusted R². This final model achieved a strong R² of 0.8758, with key predictors such as pickup/drop coordinates and distance showing high significance, while time-related variables had minimal impact and no collinearity.

![image](https://github.com/user-attachments/assets/8beccd4e-8ca8-49ca-8f68-35591e4da420)
![image](https://github.com/user-attachments/assets/65f9caa0-5d44-42a0-8de0-25cbbf56c75c)
![image](https://github.com/user-attachments/assets/3a0b9160-3960-470f-9796-a70021b972f1)



## Conclusion
The analysis of the January 2013 Uber dataset revealed many influential points, but through effective feature engineering, a predictive model was built with 87.5% accuracy. Key features influencing fare included pickup and drop-off coordinates and distance, confirming that ride fare is largely driven by travel distance. However, pickup time (pickup_datetime) showed no significant linear relationship with fare in this dataset.
