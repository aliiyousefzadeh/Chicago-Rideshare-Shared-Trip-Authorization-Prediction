# Chicago Rideshare Shared Trip Authorization Prediction
This project is focused on predicting the likelihood of shared trip authorizations for rideshare services in the city of Chicago.

# Introduction
This project aims to predict if a trip in the city of Chicago will be shared or not, using the Transportation Network Providers Trips dataset provided by the City of Chicago. The dataset includes information about all trips taken from November 2018 until January 2023.

# Data Inspection
To get a better inspect of the data, here is a chart to show the ratio of shared and non-shared trips:<br>
![Alt Text](https://github.com/aliiyousefzadeh/Chicago-Rideshare-Shared-Trip-Authorization-Prediction/blob/main/Shared_ratio_pie_chart.PNG?raw=true)<br>
About 85% of the data is non-shared and the other is shared trips.<br>
<br>
The number of trips taken on each day is as follows:<br><br>
![Alt Text](https://github.com/aliiyousefzadeh/Chicago-Rideshare-Shared-Trip-Authorization-Prediction/blob/main/days_data.PNG?raw=true)<br>
Friday and Saturday are the most favorite days for both shared and non-shared trips.<br>
<br>
Also, to separate the trips into hours, the following chart shows the trend of trips during the hours of a day:<br>
![Alt Text](https://github.com/aliiyousefzadeh/Chicago-Rideshare-Shared-Trip-Authorization-Prediction/blob/main/hourly_trips.PNG?raw=true)<br>
The data highlights that 8 AM is the first peak hour, especially for shared trips, and then from 5 PM until 7 PM there is another peak period for both types of trips.<br>
The favorite hour for shared trip is 5 PM, while for non-shared it's 6 PM.



# Project Overview
The prediction model is based on five factors:<br>
1- The starting hour of the trip<br>
2- The district the trip is starting from<br>
3- The distance<br>
4- The target district<br>
5- The cost of a typical trip based on the aforementioned factors.<br>
6- The day of the week the trip is taken<br>

The dataset is imbalanced, with a significantly lower percentage of shared trips. To avoid bias in the prediction model, we selected an equal number of shared and not_shared trips to create a balanced dataset.

We used Python and various libraries including pandas, numpy, and scikit-learn to preprocess the data, perform feature engineering, and train and test machine learning models. We experimented with six different architectures and evaluated their performance using cross-validation. We then chose the best model based on its accuracy and other metrics.

# Technical Description
The code first imports the necessary libraries such as numpy, pandas, and scikit-learn. It also installs the Bayesian optimization library. Then it mounts the Google Drive to read a CSV file. After reading the CSV file into a pandas dataframe, the code then explores data by counting the number of shared and non-shared trips and comparing the duration and distance of shared and non-shared trips.

Next, the code modifies the dataset by converting the "Trip Start Timestamp" and "Trip End Timestamp" columns to datetime objects, extracting the hour from these columns, dropping irrelevant columns from the dataframe, and converting the "Shared Trip Authorized" column to an integer.

Afterward, the code selects the relevant features for the model and splits the data into training, validation, and testing sets. Then it defines 6 different architectures of neural network models to find the best model.

Then all the models are compiled and trained with the validation dataset and evaluated to find the best model which would be selected based on their loss function values.

The Arcitecture of final model is follows:<br>
![Alt Text](https://github.com/aliiyousefzadeh/Chicago-Rideshare-Shared-Trip-Authorization-Prediction/blob/main/model.png?raw=true)<br>

After selecting the final model, the model is trained using training set and evaluated with testing set.

# Results
Our best model achieved an accuracy of 89%, which is a significant improvement, with a loss of 0.29. This indicates that our model is able to make relevantly accurate predictions on whether a trip will be shared or not. Considering only using 6 factors to see if a trip will be shared or not, we achieved a reasonable accuracy.

# Acknowledgment
We would like to acknowledge the City of Chicago for providing the [Transportation Network Providers Trips dataset](https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips/m6dm-c72p) used in this project.

# Future Improvements
In the future, we plan to explore additional factors that could impact trip sharing, such as weather conditions and time of the year (like months and seasons). We also plan to investigate more advanced machine learning techniques to improve the accuracy of our prediction model.
